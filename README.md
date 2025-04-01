# **Homomorphic Watermarking**

## **Overview**
This project implements a watermarking system for images encrypted with the Paillier cryptosystem. It combines Quantization Index Modulation (QIM) and homomorphic encryption to embed a watermark into an encrypted image, ensuring both security and robustness.

## **Description**
The code implements the following steps:

1. **Paillier Key Generation:** Generates public and private keys to encrypt the data.
2. **Paillier Encryption:** Encrypts each pixel in the image before embedding the watermark.
3. **Quantization Index Modulation (QIM):** Modifies pixel values according to the watermark bits using QIM.
4. **Watermark Insertion:**
   - 4.1 **In the Clear Domain:** Multiply the encrypted pixels by the encrypted watermark.
   - 4.2 **In the Encrypted Domain:** Adjust the encrypted pixel representations until the least significant bit matches the watermark bit.
5. **Watermark Extraction:**
   - 5.1 **From the Encrypted Domain:** Recover the watermark bits directly.
   - 5.2 **From the Clear Domain:** Decrypt the pixels and compare with the predefined watermark.
6. **Image Display:** Display the original image and the decrypted image with the watermark.

## **Code Structure**
The following functions are implemented in the code:

- **`get_prime(size)`**: Generates a prime number of a specified bit size.
- **`get_paillier_keys(size)`**: Generates Paillier public and private keys.
- **`paillier_encrypt(message, pub_key)`**: Encrypts a message using the public key.
- **`paillier_decrypt(enc, priv_key, pub_key)`**: Decrypts an encrypted message.
- **`QIM(w, p, delta)`**: Applies Quantization Index Modulation to the image.
- **`insertion_clair(pwe, b, pub_key)`**: Inserts the watermark into the clear domain.
- **`insertion_ciphered(pweb, b, pub_key)`**: Inserts the watermark into the encrypted domain.
- **`extraction_ciphered(image)`**: Extracts the watermark from the encrypted domain.
- **`watermark_image(image, w, b)`**: Applies the watermark to the image.

## **Requirements**
- **Python:** 3.12
- **Libraries:**  
  - `numpy`
  - `gmpy2`
  - `matplotlib`
  - `opencv-python`
  
  To install the necessary libraries, run:
  ```bash
  pip install numpy gmpy2 matplotlib opencv-python  
- **Input Image:** `128p.jpg`

## **References**
1. Dalel Bouslimi, Reda Bellafqira, and Gouenou Coatrieux. Data hiding in homomorphically encrypted medical images for verifying their reliability in both encrypted and spatial domains. In 2016 38th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pages 2496–2499. IEEE, 2016.
2. Brian Chen and Gregory W. Wornell. Quantization index modulation: A class of provably good methods for digital watermarking and information embedding. IEEE Transactions on Information Theory, 47(4):1423–1443, 2001.
3. Pascal Paillier. Public-key cryptosystems based on composite degree residuosity classes. In International Conference on the Theory and Applications of Cryptographic Techniques, pages 223–238. Springer, 1999..
