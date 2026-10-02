# Cryptography and Tokens

## Hashing & Secure Comparison

- Cryptographic Hash Functions: One-way transformations (`SHA-256`, `MD5`).

- Salting & Stretching: Adding unique random data (salt) to inputs before hashing to prevent rainbow table attacks.

- Constant-Time Comparison: Use `hmac.compare_digest()` to prevent timing attacks when validating hashes or tokens.

<br/>

```python
import hashlib
import hmac
import secrets

# Hashing with Salt
salt = secrets.token_bytes(16)
password = "secure_password123".encode('utf-8')
hashed = hashlib.pbkdf2_hmac('sha256', password, salt, 100000)

# Safe Comparison
is_valid = hmac.compare_digest(hashed, hashed)
```

<br/>

## JSON Web Tokens (JWT)

Structure: Three Base64Url-encoded strings separated by dots: `Header.Payload.Signature`

- Header: Algorithm used (`HS256`, `RS256`) and token type (`JWT`).

- Payload: Claims/data (e.g., `user_id`, `exp` expiration time).

- Signature: Calculated by taking the encoded header, payload, and a secret key using the specified algorithm.

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
\_________________________________/ \__________________________________________________/ \__________________________________________________/
              Header                                      Payload                                                    Signature
```

<br/>

## Common Exam Pitfalls

- Decoding vs. Verifying: Base64 decoding a JWT reveals its payload without verifying authenticity. The signature must be verified using the secret key before trusting claims.

- `secrets` vs `random`: The built-in `random` module uses Mersenne Twister and is not cryptographically secure. Use the `secrets` module for tokens, keys, or security-sensitive operations.
