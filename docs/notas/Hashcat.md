---
tags: [cracking,passwords]
---

# Hashcat
Esta herramienta nos permite recuperar contraseñas y secretos. Es compatible con una amplia variedad de algoritmos de hash.

Puedes encontrar el listado completo en la documentación oficial de Hashcat [aquí](https://hashcat.net/hashcat/).


## Sintaxis básica
El esquema básico de uso de Hashcat es el siguiente:

```bash
hashcat [opciones] hash.txt [diccionario.txt]
```

Las opciones entre corchetes son opcionales. El archivo `hash.txt` es el archivo que contiene los hashes de las contraseñas que queremos descifrar. El archivo `diccionario.txt` es un archivo que contiene una lista de palabras o frases comunes que se utilizarán para intentar descifrar los hashes.

La opción `-m` se utiliza para especificar el tipo de hash que se está intentando descifrar. Por ejemplo, `-m 0` se utiliza para especificar que el hash es un hash de MD5.



## Tipos de ataque
**Ataque de fuerza bruta**: Para realizar un ataque de fuerza bruta con Hashcat, puedes utilizar el siguiente comando. Este comando intentará todas las combinaciones posibles de la contraseña.

```bash
hashcat -m 0 -a 3 hash.txt
```

**Ataque de diccionario**: Un ataque de diccionario intenta adivinar la contraseña utilizando una lista de palabras o frases comunes. Para realizar un ataque de diccionario con Hashcat, puedes usar el siguiente comando:

```bash
hashcat -m 0 -a 0 hash.txt dictionary.txt
```

**Ataque de combinación**: Un ataque de combinación intenta adivinar la contraseña combinando palabras de dos diccionarios diferentes. Para realizar un ataque de combinación con Hashcat, puedes usar el siguiente comando:

```bash
hashcat -m 0 -a 1 hash.txt dictionary1.txt dictionary2.txt
```

**Ataque de máscara**: Un ataque de máscara intenta adivinar la contraseña aplicando una máscara a un patrón de contraseña conocido. Para realizar un ataque de máscara con Hashcat, puedes usar el siguiente comando:

```bash
hashcat -m 0 -a 3 hash.txt ?a?a?a?a?a?a?a?a?d?d
```

**Ataque con reglas**: Un ataque con reglas intenta adivinar la contraseña aplicando reglas a una lista de palabras o frases comunes. Para realizar un ataque con reglas con Hashcat, puedes usar el siguiente comando:

```bash
hashcat -m 0 -a 0 -r rules.txt hash.txt dictionary.txt
```
