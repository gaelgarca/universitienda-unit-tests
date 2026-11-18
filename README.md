# Universitienda backend: pruebas unitarias de utilitarios

Actividad: pruebas unitarias de utilitarios con **Vitest y TypeScript**
sobre el backend de Universitienda.

## Archivos de prueba

```text
tests/
└── src/
    └── utils/
        ├── password.test.ts      # hashPassword / comparePassword (bcrypt)
        └── generateCode.test.ts  # generateSixDigitCode
```

### password.test.ts

Usa `password1 = "ClaveUno123!"` y `password2 = "ClaveDos456!"`, genera
`hash1` y `hash2` con `hashPassword` y comprueba:

| Caso | Resultado esperado |
| --- | --- |
| Generación de hashes | Cada hash es una cadena no vacía y diferente de su contraseña. |
| Contraseña correcta | `comparePassword(password1, hash1)` y `comparePassword(password2, hash2)` devuelven `true`. |
| Contraseña incorrecta | `comparePassword(password2, hash1)` y `comparePassword(password1, hash2)` devuelven `false`. |

Se usan las funciones reales, sin simular bcrypt.

## Ejecutar

```bash
npm install
npm test -- tests/src/utils/password.test.ts tests/src/utils/generateCode.test.ts
```
