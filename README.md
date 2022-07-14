# DigitalSignature
Digital signature script using RSA



Firstly, the source part’s ID is read from the ID.txt file. Then it gets hashed using
SHA256. Then, that hash value gets encrypted with KH key. KH is created by using the
XOR(Source private key, destination public key). After that, we concatinate the encrypted
hash value with our source file. Then, Session Key is created and used for encrypting the
concatinated source and encrypted hash value. In order to sen Session Key safely, we encrypt
the Session Key itself using destination public key. We are able to do this since public keys
are open to the world. In the destination part, first thing we do is to decrypt the Session key so
that we can use it for decrypting our concatinated source file and hash value. Later, we
wanted to unlock concatinated file with KH in order to compare it’s hash value with newly
computed hash value for authentication.
