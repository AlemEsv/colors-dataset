# Dígitos de Colores

## Qué es

Aplicación web interactiva para dibujar dígitos (0-9) en diferentes colores y guardarlos como dataset. Los usuarios dibujan números en un canvas HTML5 con colores aleatorios, y las imágenes se almacenan localmente y pueden subirse automáticamente a GitHub.

## Requisitos

- Python 3.8+
- Cuenta GitHub (opcional, para subir imágenes)
- Token personal de GitHub (opcional)

## Quickstart

### Instalar

```bash
pip install -r requirements.txt
```

### Configurar

Crea un archivo `.env` en la raíz del proyecto (opcional):

```env
GITHUB_TOKEN=tu_token_aqui
PORT=5000
```

### Ejecutar

```bash
python main.py
```

Abre tu navegador en `http://localhost:5000`

## Configuración

| Variable | Descripción | Valor por defecto |
|----------|-------------|-------------------|
| `GITHUB_TOKEN` | Token para subir imágenes a GitHub | - |
| `PORT` | Puerto del servidor | 5000 |

## Uso

1. Abre la aplicación en tu navegador
2. Se mostrará un número aleatorio (0-9) y un color aleatorio
3. Dibuja el número con el color indicado en el canvas
4. Haz clic en "Enviar" para guardar
5. Las imágenes se guardan en carpetas numeradas (0/ a 9/)
6. Usa `/commit` para subir las imágenes a GitHub (requiere token)

## Estructura

```txt
├── main.py              # Aplicación Flask principal
├── requirements.txt     # Dependencias Python
├── Procfile            # Configuración para despliegue
├── .env                # Variables de entorno (crear)
├── 0/ a 9/             # Carpetas con imágenes de dígitos
└── README.md           # Este archivo
```

- `main.py`: Servidor Flask con canvas HTML5 y API GitHub
- Carpetas `0/` a `9/`: Almacenan imágenes PNG de cada dígito
- Canvas genera imágenes de 200x200 px

## Problemas comunes

**Error: "token no configurado"**

- Crea el archivo `.env` con tu `GITHUB_TOKEN`

**La aplicación no arranca**

- Verifica que instalaste todas las dependencias: `pip install -r requirements.txt`
- Comprueba que el puerto 5000 esté libre

**Las imágenes no se guardan**

- Asegúrate de tener permisos de escritura en el directorio
- Las carpetas 0-9 se crean automáticamente

**Error al subir a GitHub**

- Verifica que tu token tenga permisos de escritura en el repositorio
- Revisa que el nombre del repositorio en `main.py` sea correcto (líneas 167-168)
