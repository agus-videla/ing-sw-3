# Trabajo Práctico 10

## 1

El objeto `I` es un proxy para acceder a los `helpers` habilitados.

## 2

Luego de seguir los pasos y editar "github_test.ts" el test corre correctamente:

```bash
❮ npx codeceptjs run --steps 
context 
CodeceptJS v3.3.6 #StandWithUkraine 
Using test root "/home/agus/Documents/facultad/cursada_2022/ing-sw-3/recursos/codecept" 
github -- 
  test something 
    I am on page "https://github.com" 
    I see "GitHub" 
    I see "Open Source" 
    I scroll page to bottom 
    I see element "//li[contains(.,'© 2022 GitHub, Inc.')]" 
  ✔ OK in 2052ms 
  OK  | 1 passed   // 3s 
```

