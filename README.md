# Tiny AES in CPP

## Memory safety

* Not using pointers, pointer casting and whatever potentially dangerous stuff unless absolutely necessary.
* Only deterministic and transparent types are aavailable through public API functions.

## API

```
/**
 * Encrypt or decrypt blocks with AES256-CTR
 *
 * @param out Vector of blocks
 * @param sk Secret key
 * @param counter AES counter
 * @param blocks Number of blocks to encrypt
 */
void aesctr256(std::vector<aes_block_t>& out, const aes_key_t &sk, const aes_block_t &counter);
```

```
/**
 * Encrypt or decrypt one block with AES256-CTR
 *
 * @param block Data block
 * @param sk Secret key
 * @param counter AES counter
 * @param blocks Number of blocks to encrypt
 */
void aesctr256(aes_block_t& block, const aes_key_t &sk, const aes_block_t &counter);
```

Notes: `aes_key_t` and `aes_block_t` are std::array<uint8_t> of key size and std::array<uint8_t> of AES block size respectively..

## Original project

See https://github.com/kokke/tiny-AES-c for additional information.

## Limitations

Only AES256-CTR is available for now.
