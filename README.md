# Github CV

# Modern Resume Theme - Configuración Local

Este proyecto utiliza el [Modern Resume Theme](https://sproogen.github.io/modern-resume-theme/) para crear un portafolio personal elegante y totalmente personalizable. A continuación, se explican los pasos que seguí para configurarlo localmente en Windows y las modificaciones realizadas para adaptarlo a mis necesidades.

---

## 🔧 Requisitos

Antes de empezar, asegúrate de tener instalados los siguientes programas:

- **Ruby**: Versión 2.7 o superior.
- **Bundler**: Administrador de dependencias de Ruby.

---

## 🚀 Instrucciones de Configuración

### 1. Clonar el Repositorio

Descarga o clona el repositorio del Modern Resume Theme desde GitHub:

```bash
git clone https://github.com/sproogen/modern-resume-theme.git
cd modern-resume-theme
```

También puedes descargar los archivos de plantilla desde [la página oficial](https://sproogen.github.io/modern-resume-theme/).

---

### 2. Instalar Ruby en Windows

Descarga Ruby desde [RubyInstaller](https://rubyinstaller.org/downloads/) y sigue los pasos de instalación. Durante la configuración, asegúrate de habilitar la opción para instalar MSYS2, ya que es necesario para las dependencias de Ruby.

---

### 3. Actualizar el Archivo `Gemfile`

Para que el proyecto funcionara correctamente en mi entorno, modifiqué el archivo `Gemfile`, actualizando la versión del gem `wdm` a `~> 0.2.0`. Aquí está el contenido actualizado del archivo:

```ruby
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins

# Windows no incluye archivos zoneinfo, así que se incluye el gem tzinfo-data
gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]

# Optimizador de rendimiento para monitorear directorios en Windows
gem "wdm", "~> 0.2.0" if Gem.win_platform?
```

---

### 4. Instalar las Dependencias

Ejecuta el siguiente comando para instalar las dependencias necesarias:

```bash
bundle install
```

---

### 5. Inicializar el Proyecto Localmente

Para visualizar el portafolio en tu navegador, ejecuta:

```bash
bundle exec jekyll serve
```

El portafolio estará disponible en `http://localhost:4000`.

---

## 🛠️ Modificaciones Realizadas

- **Actualización del Gemfile**: Se actualizó la versión del gem `wdm` para garantizar compatibilidad con Windows.
- **Edición de Contenido**: Personalicé el portafolio editando el archivo `config.yml` para reflejar mi experiencia, proyectos y habilidades.

---

## 🔄 Flujo de Trabajo

1. Edita el archivo `config.yml` para actualizar el contenido de tu portafolio.
2. Recarga el navegador para visualizar los cambios en tiempo real.
3. Una vez terminado, puedes subir el portafolio a GitHub Pages para alojarlo en línea.

---

## 💡 Notas

- Asegúrate de que tu versión de Ruby sea compatible con los requisitos especificados en la [documentación del Modern Resume Theme](https://github.com/sproogen/modern-resume-theme).
- Si encuentras problemas, verifica las versiones de Ruby y Bundler, o consulta la [FAQ de RubyInstaller](https://rubyinstaller.org/support).
