Introduction:
In this assignment, we will aim to develop a signature verification protocol using the
RSA algorithm.
The RSA public-key cryptosystem provides a digital signature scheme (sign + verify),
based on the math of the modular exponentiations and discrete logarithms and the
computational difficulty of the RSA problem.
Steps for RSA sign/verify algorithm:
● Key Generation:- The RSA key-pair consists of: public key {n, e} & private key
{n, d}. The numbers n and d are typically big integers, while e is small. By
definition, the RSA key-pairs has the following property:
(m^e)^d ≡(m^d)^e ≡m(modn), for all m in the range [0...n)
● RSA Sign:- sign a message ‘msg’ with the private key components {n,d}
○ Calculate the message hash: h = hash(msg)
○ Encrypt h to calculate the signature: s = h^d (mod n)
● RSA Verify Signature:- Verify a signature s for the message ‘msg’ with the
public key {n, e}
○ Calculate the message hash: h = hash(msg)
○ Decrypt the signature: h′ =s^e (mod n)
○ Compare h with h' to find whether the signature is valid or not
Task:
Signature_Verification_Starter.ipynb
1. Task-1: Understand how the ‘pycryptodome’ package works in generating
private key and public keys for encryption and decryption using RSA
2. Task-2: Verify the signature using RSA algorithm
a. Generate private and public keys using RSA for signature verification
b. Sign the message using the private key.
i. Define a message called ‘msg’ for verification
ii. Compute the hash message [Hint:- use the SHA256 from
Crypto.Hash]
iii. Generate the signature ‘sign’ for the above hash message [Hint:- use
pkcs1_15 from Crypto.Signature]
c. The receiver has received the signature and the message from the sender.
Verifying the above signature ‘sign’ for the message ‘msg’ using the above public key
i. Calculate a hash (hash1) of the received message ‘msg’ [Hint:- use
the SHA256 from Crypto.Hash]
ii. Compare the hash1 and the hash amc comment whether the
signature is original or not.
iii. If 'hash1' (from received message) is same as the 'hash' (from sent
message), we will get to know that message is original.
d. Make some changes to the message or signature and then verify the signature.
Note:- Try to save all the keys, messages, and signature in the files.
The final submission of this lab assessment should be made on Olympus.
Note: The file should be submitted in .ipynb and .HTML (both) formats.
