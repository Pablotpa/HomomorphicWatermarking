# Homomorphic Watermarking
Overview
This project implements a watermarking system for images encrypted with the Paillier cryptosystem. The approach combines Quantization Index Modulation (QIM) and homomorphic encryption to embed a watermark into an encrypted image, ensuring security and robustness.

Description

The code implements the following steps:
1. Paillier Key Generation: Public and private keys are generated to encrypt the data.
2. Paillier Encryption: Each pixel in the image is encrypted before embedding the watermark.
3. Quantization Index Modulation (QIM): QIM is used to modify pixel values ​​according to the watermark bits.
4. Watermark Insertion:
  4.1 In the clear domain: Multiply the encrypted pixels by the encrypted watermark.
  4.2 In the encrypted domain: The encrypted representation of the pixels is adjusted until the least significant bit matches the watermark bit.
5. Watermark Extraction:
  5. 1 From the encrypted domain: The bits are recovered directly.
  5.2 From the clear domain: The pixels are decrypted and compared with the predefined watermark.
6. Image Display: The original image and the decrypted image with the watermark are displayed.


Code Structure
- get_prime(size): Generates a prime number of size bits.
- get_paillier_keys(size): Generates the Paillier public and private keys.
- paillier_encrypt(message, pub_key): Encrypts a message using the public key.
- paillier_decrypt(enc, priv_key, pub_key): Decrypts an encrypted message.
- QIM(w, p, delta): Applies quantization index modulation.
- insertion_clair(pwe, b, pub_key): Inserts the watermark into the clear domain.
- insertion_ciphered(pweb, b, pub_key): Inserts the watermark into the encrypted domain.
- extraction_ciphered(image): Extracts the watermark from the encrypted domain.
- watermark_image(image, w, b): Applies the watermark to an image.

Requirements
- Python 3.12
- Necessary libraries: pip install numpy gmpy2 matplotlib opencv-python
- Input image 128p.jpg

Références
1. Dalel Bouslimi, Reda Bellafqira, and Gouenou Coatrieux. Data hiding in homomorphically encrypted medical images for verifying their reliability in both encrypted and spatial domains. In 2016 38th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pages 2496–2499. IEEE, 2016.
2. Brian Chen and Gregory W Wornell. Quantization index modulation : A class of provably good methods for digital watermarking and information embedding. IEEE Transactions on Information theory, 47(4) :1423–1443, 2001.
3. Pascal Paillier. Public-key cryptosystems based on composite degree residuosity classes. In International conference on the theory and applications of cryptographic techniques, pages 223–238. Springer, 1999.


Auteurs
- CENZANO ALIAGA Anthony
  Cybersecurity Engineering Student - IMT Atlantique
- TRONCOSO PAREJA Pablo
  Cybersecurity Engineering Student - IMT Atlantique
