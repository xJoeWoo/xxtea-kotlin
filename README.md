# XXTEA for Kotlin

# Introduction
XXTEA encryption algorithm library for Kotlin.
Import from `[xxtea-java](https://github.com/xxtea/xxtea-java)` with `[version 1.0.5](https://github.com/xxtea/xxtea-java/tree/2c332d1f03eb62b829e9d3dab10318770e4b7d4c)`

## Usage
First, copy coresponding platform source file to your project:
  - [JVM, Android](jvm/XXTEA.kt) (**Better to fix package info with your own package path on top of this source file**)
  - [Native](native/XXTEA.kt)

Second:
```kotlin
fun main() {
  
    // ------------- String -------------
    val str = "Hello World! 你好，中国！"
    val key = "1234567890"
    
    // Returns null if decode from string to byte array fails
    val encryptData = XXTEA.encrypt(str, key) 

    // Default encoding is UTF_8. To use other encoding:
    // val encryptData = XXTEA.encrypt(str, key, Charsets.US_ASCII)
    // val encryptData = XXTEA.encrypt(str, key, Charset.forName("GBK"))
    
    val decryptData = XXTEA.decryptToString(encryptData!!, key)
    assert(str == decryptData)


    // ------------- ByteArray -------------
    val strBytes = str.toByteArray()
    val keyBytes = key.toByteArray()
    val encryptBytesData = XXTEA.encrypt(strBytes, keyBytes)
    val decryptBytesData = XXTEA.decrypt(encryptBytesData, keyBytes)
    assert(strBytes.contentEquals(decryptBytesData))
}
```

### Encoding
If you need to change default encoding of `XXTEA`, just call
```
XXTea.defaultCharset = [charset]
```
before use it.

