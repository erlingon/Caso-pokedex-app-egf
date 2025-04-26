Claro, aquí tienes el contenido reorganizado y formateado profesionalmente para un archivo `README.md` en GitHub:

---

# 🧩 Pokédex Frontend - Despliegue en Azure

Este proyecto es una aplicación frontend desarrollada en **Angular**, que consume datos desde la [PokéAPI](https://pokeapi.co/). Como parte del proceso, se realizaron configuraciones de seguridad y despliegue para alojarla como una **Static Web App en Azure**.

---

## 🔧 Tecnologías utilizadas

- **Angular**
- **Azure Static Web Apps**
- **PokéAPI**

---

## 🚀 Funcionalidades principales

- Visualización de **GIFs de Pokémon**.
- Consumo de datos desde una **API externa (PokéAPI)**.
- Configuración personalizada de **encabezados de seguridad**.
- **Despliegue en la nube** mediante Azure.

---

## 📦 Instalación y ejecución local

```bash
git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo
npm install
ng serve
```

---

## 📄 Guía de Despliegue en Azure

### 1. Fork y configuración inicial

- Se realizó un fork del repositorio original.
- Se trabajó en una copia local del proyecto.
- Se actualizó `src/environments/environment.ts` para mejorar la visualización de GIFs en producción.

### 2. Configuración de seguridad

- Azure incluye **3 encabezados HTTP de seguridad por defecto** gracias al uso de HTTPS.
- Se añadieron manualmente otros **3 encabezados recomendados**, logrando una calificación de seguridad **A**.
- ⚠️ *Nota:* No se alcanzó la calificación A+ debido a la política `Content-Security-Policy`. La directiva `unsafe-inline` no pudo configurarse de forma segura sin generar errores 500.

### 3. Despliegue en Azure

#### Creación del recurso

- Se creó un recurso de tipo **Static Web App**.
- La vinculación automática con el repositorio falló inicialmente, ya que el flujo de trabajo no encontraba el código fuente.

#### Solución aplicada

- Se editó el archivo de workflow generado por Azure:  
  `.github/workflows/azure-static-web-apps.yml`
- Se ajustó la propiedad `app_location` para que apuntara al directorio correcto (por ejemplo: `"/"`).

#### Resultado

- ✅ **Despliegue exitoso.**
- La aplicación quedó funcional y disponible públicamente.

### 4. Validación final

- Se ejecutó un escaneo de seguridad.
- Resultado final: **Calificación A**.
- Mejora pendiente: ajustar la **CSP** para permitir carga segura de scripts externos sin comprometer la seguridad.
