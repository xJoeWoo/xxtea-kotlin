# XXTEA for Kotlin

# Introduction
XXTEA encryption algorithm library for Kotlin.
Import from [xxtea-java](https://github.com/xxtea/xxtea-java) [version 1.0.5](https://github.com/xxtea/xxtea-java/tree/2c332d1f03eb62b829e9d3dab10318770e4b7d4c)

## Usage
Copy the [source file](#) to your project, remember to fix with your own package path on top of source file.

```kotlin
fun main() {
  
    // String
    val str = "Hello World! 你好，中国！"
    val key = "1234567890"
    val encryptData = XXTEA.encrypt(str, key)
    val decryptData = XXTEA.decryptToString(encryptData!!, key)
    assert(str == decryptData)

    // ByteArray
    val strBytes = str.toByteArray()
    val keyBytes = key.toByteArray()
    val encryptBytesData = XXTEA.encrypt(strBytes, keyBytes)
    val decryptBytesData = XXTEA.decrypt(encryptBytesData, keyBytes)
    assert(strBytes.contentEquals(decryptBytesData))
}
```

