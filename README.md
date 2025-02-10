# Guía de Instalación y Ejecución de la Aplicación en Python

## Instalación de Python 3

### Windows
1. Descarga el instalador de Python desde la página oficial: [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. Ejecuta el instalador y asegúrate de marcar la opción **"Add Python to PATH"**.
3. Haz clic en **"Install Now"** y espera a que termine la instalación.
4. Para verificar la instalación, abre la terminal (**cmd** o **PowerShell**) y ejecuta:
   ```sh
   python --version
   ```

### Linux
1. Abre una terminal y actualiza la lista de paquetes:
   ```sh
   sudo apt update  # Para distribuciones basadas en Debian (Ubuntu, etc.)
   sudo dnf update  # Para Fedora
   sudo pacman -Syu  # Para Arch Linux
   ```
2. Instala Python 3:
   ```sh
   sudo apt install python3  # Debian/Ubuntu
   sudo dnf install python3  # Fedora
   sudo pacman -S python  # Arch Linux
   ```
3. Verifica la instalación:
   ```sh
   python3 --version
   ```

## Instalación y Activación de pip

### Windows
Pip se instala automáticamente con Python. Para verificarlo, ejecuta en la terminal:
```sh
pip --version
```
Si no está instalado, usa:
```sh
python -m ensurepip --default-pip
```

### Linux
Pip generalmente viene preinstalado, pero si no, puedes instalarlo con:
```sh
sudo apt install python3-pip  # Debian/Ubuntu
sudo dnf install python3-pip  # Fedora
sudo pacman -S python-pip  # Arch Linux
```
Verifica la instalación con:
```sh
pip3 --version
```

## Creación y Activación de Entorno Virtual

### Windows
1. Crea el entorno virtual:
   ```sh
   python -m venv venv
   ```
2. Activa el entorno:
   ```sh
   venv\Scripts\activate
   ```
   Para desactivarlo, usa:
   ```sh
   deactivate
   ```

### Linux
1. Crea el entorno virtual:
   ```sh
   python3 -m venv venv
   ```
2. Activa el entorno:
   ```sh
   source venv/bin/activate
   ```
   Para desactivarlo:
   ```sh
   deactivate
   ```

## Instalación de Dependencias
Con el entorno virtual activado, instala las dependencias del proyecto:
```sh
pip install -r requirements.txt
```
Si no tienes el archivo `requirements.txt`, puedes generarlo con:
```sh
pip freeze > requirements.txt
```

## Ejecución de la Aplicación
Para ejecutar la aplicación, usa:
```sh
python app.py  # O el nombre del script principal
```
Si el script usa Python 3 específicamente:
```sh
python3 app.py
```

## Ejemplo: Aplicación con PySide6
Si la aplicación usa `PySide6`, un ejemplo de código con un "Hola Mundo" sería:

```python
from PySide6.QtWidgets import QApplication, QLabel
import sys

app = QApplication(sys.argv)
label = QLabel("¡Hola Mundo!")
label.show()
sys.exit(app.exec())
```

Para ejecutar este código, asegúrate de instalar `PySide6` con:
```sh
pip install PySide6
```
Luego, ejecuta el script:
```sh
python app.py
```
