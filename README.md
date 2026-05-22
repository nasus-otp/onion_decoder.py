# onion_decoder.py

# 🧅🕵️‍♂️ Onion Decoder

**Onion Decoder ** es una herramienta avanzada de análisis y desofuscación de payloads para Pentesters, Analistas de Malware y jugadores de CTF. 

A diferencia de los decodificadores estáticos, esta herramienta utiliza un motor iterativo que detecta y "pela" automáticamente múltiples capas de codificación hasta revelar el texto plano o el shellcode subyacente.

---

## 🔥 Características Profesionales

* **Detección Automática Multicapa:** Soporta y encadena decodificaciones sin necesidad de especificar el orden.
* **Formatos Soportados:**
  * Base64 y Base64URL (con autocorrección de *padding* faltante).
  * URL Encoding (URL Decode).
  * Hexadecimal (`0x41`, `\x41`, `4141`).
  * Binario a ASCII (`01000001`).
  * HTML Entities (`&lt;script&gt;`).
  * ROT13 (Activación inteligente).
* **Manejo de Binarios Crudos:** Si una capa Base64 esconde un archivo ejecutable (.exe, .elf) o un *shellcode* en lugar de texto legible, el script no falla; lo captura y devuelve un volcado hexadecimal limpio (`Hex Dump`) para análisis forense.
* **Control de Falsos Positivos:** Utiliza Expresiones Regulares (Regex) para validar heurísticamente si una cadena es realmente Hexadecimal o Binario antes de intentar decodificarla.

---

## 🚀 Instalación y Uso

Clona el repositorio y ejecuta el script con Python 3 (no requiere librerías externas).

git clone [https://github.com/nasus-otp/onion-decoder.git](https://github.com/nasus-otp/onion-decoder.git])
cd onion-decoder

## Ejecución Básica

Pasa el payload ofuscado y deja que el motor haga el resto:

python3 onion_decoder_pro.py -t "PAYLOAD_AQUI"

## Búsqueda de Palabra Clave (Target Word)

Ideal para detener la ejecución cuando encuentras lo que buscas (ej. una flag, un comando SQL, una contraseña):

python3 onion_decoder_pro.py -t "PAYLOAD_AQUI" -w "SELECT"
