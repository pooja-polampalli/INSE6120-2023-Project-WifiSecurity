# INSE6120-2023-Project-WifiSecurity
Wifi Security hacking using FMS and PTW

FMS Attack on WEP Encryption - Python Implementation

This Python implementation demonstrates the Fluhrer, Mantin, and Shamir (FMS) attack on Wired Equivalent Privacy (WEP) encryption. It includes a simple implementation of WEP encryption and decryption using RC4, as well as an implementation of the FMS attack itself.

Note: WEP encryption is considered insecure and is not recommended for use in real-world applications. This implementation is for educational purposes only.

Overview

The code provided contains the following functions:

rc4(key, data): The RC4 encryption/decryption algorithm.
wep_encrypt(key, data): WEP encryption using RC4 and a random 24-bit IV.
wep_decrypt(key, encrypted_data): WEP decryption using RC4.
fms_attack(ciphertexts, known_prefix, key_length=5): FMS attack on WEP encryption.
The main() function demonstrates the FMS attack by first simulating the WEP encryption and collecting ciphertexts. It then performs the FMS attack to recover the WEP key and uses the recovered key to decrypt a message.

How it works

WEP encryption and decryption:
WEP encryption combines a user-provided secret key and a randomly generated 24-bit initialization vector (IV) to form an extended key.
The extended key is used as input to the RC4 algorithm, which then generates a ciphertext.
WEP decryption reverses the process by using the same extended key to decrypt the ciphertext back into the original plaintext.
FMS attack:
The FMS attack exploits a weakness in the RC4 algorithm where certain key values can lead to a biased output distribution.
By collecting a large number of ciphertexts encrypted under different IVs, the FMS attack can recover the WEP key by analyzing the frequency of certain bytes in the ciphertexts.
The FMS attack assumes knowledge of a known prefix of the plaintext data, which is often true in the case of WEP-encrypted network traffic.

Usage -

Run the script using Python 3:

python3 fms_attack_wep.py
The script will simulate WEP encryption and perform the FMS attack, printing the recovered key and decrypted message to the console.

Note - The current implementation simulates the process of capturing packets by generating ciphertexts using the wep_encrypt() function. While this demonstrates the concept of the FMS attack, it does not utilize actual captured packets.










