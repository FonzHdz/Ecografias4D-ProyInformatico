# 🏥 Proyecto Informático - Sistema de Gestión de Ecografías 4D

<div align="center">

  <br /><br />
  [![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)](https://dotnet.microsoft.com/es-es/languages/csharp)
  [![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)](https://dotnet.microsoft.com/)
  [![MongoDB](https://img.shields.io/badge/MongoDB-3.0-47A248?logo=mongodb)](https://www.mongodb.com/)
  [![Azure](https://img.shields.io/badge/Azure-Blob%20Storage-0078D4?logo=microsoft-azure)](https://azure.microsoft.com/)

</div>

---

## 📝 Descripción

**Ecografías 4D** es un sistema de gestión integral diseñado para automatizar los procesos de información y documentación de un negocio familiar que ofrece servicios de ecografías 4D en la ciudad de Cali. El sistema permite gestionar pacientes, citas, diagnósticos, videos ecográficos e imágenes radiológicas, cumpliendo con estándares internacionales de gestión de información médica.

---

## 🎯 Escenario del Proyecto

El proyecto surge de la necesidad de una empresa familiar que:

- Proporciona servicios de ecografías 4D para mujeres en etapas tempranas del embarazo en Cali
- Ha experimentado un crecimiento significativo de pacientes debido al turismo médico
- Maneja actualmente la documentación e información de forma manual, con apoyo limitado de hojas de cálculo
- Requiere cumplir con estándares internacionales que esperan los pacientes en sus países de origen
- Necesita resolver cuellos de botella en la conversión de videos (AVI a MP4) y en el compartimiento de videos fetales con diagnósticos

---

## ✨ Funcionalidades Destacadas

- 👤 **Gestión de usuarios multirol** (Administrador, Especialista, Paciente)
- 📅 **Sistema de citas médicas** con seguimiento de estados
- 🎥 **Gestión de videos ecográficos** con conversión automática AVI a MP4
- 🖼️ **Procesamiento de imágenes DICOM** y radiológicas
- 📄 **Generación de diagnósticos** con PDF personalizados
- 📧 **Notificaciones por correo electrónico** con recursos multimedia
- 🔐 **Autenticación segura** con cookies y autorización basada en roles
- ☁️ **Almacenamiento en la nube** con Azure Blob Storage
- 📊 **Procesamiento de datos CSV** para importación masiva
- 🏥 **Diferenciación de personal de salud** según el tipo de servicio

---

## ⚙️ Tecnologías & Herramientas

### 🔧 **Backend**

- C# + ASP.NET Core 8.0 (MVC)
- MongoDB 3.0 (Base de datos NoSQL)
- Azure Blob Storage 12.23.0 (Almacenamiento de archivos)
- fo-dicom 5.1.4 (Procesamiento de imágenes DICOM)
- BCrypt.Net-Next 4.0.3 (Encriptación)

### 📧 **Comunicación**

- MailKit 4.8.0 + MimeKit 4.8.0 (Envío de correos electrónicos)
- Zamzar API (Conversión de videos AVI a MP4)

### 📄 **Documentos**

- iTextSharp.LGPLv2.Core 3.4.22 (Generación de PDFs)
- CsvHelper 33.0.1 (Procesamiento de archivos CSV)

### 🖼️ **Procesamiento de Imágenes**

- SkiaSharp 2.88.9 (Procesamiento de imágenes)
- System.Drawing.Common 9.0.0 (Manipulación de gráficos)
- MediaInfo.DotNetWrapper 1.0.7 (Metadatos de videos)

### 🔄 **Utilidades**

- Newtonsoft.Json 13.0.3 (Serialización JSON)

---

## 🛠️ Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/Proyecto-Informatico.git
cd Proyecto-Informatico/ProyectoInformatico
```

### 2. Configurar las dependencias

Asegúrate de tener instalado:
- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- MongoDB (local o conexión a MongoDB Atlas)
- Cuenta de Azure Storage (para Blob Storage)
- API Key de Zamzar (para conversión de videos)

### 3. Configurar appsettings.json

Edita el archivo `appsettings.json` con tus credenciales:

```json
{
  "ConnectionStrings": {
    "MongoDB": "tu-cadena-de-conexion-mongodb"
  },
  "EmailSettings": {
    "SmtpServer": "smtp.gmail.com",
    "SmtpPort": 587,
    "SenderEmail": "tu-email@gmail.com",
    "SenderPassword": "tu-contraseña-de-aplicacion"
  },
  "AzureStorage": {
    "ConnectionString": "tu-cadena-de-conexion-azure",
    "Containers": {
      "Videos": "videos",
      "Imágenes": "imagenes",
      "Firmas": "firmas"
    }
  },
  "ZamzarApiKey": "tu-api-key-zamzar"
}
```

### 4. Restaurar dependencias

```bash
dotnet restore
```

### 5. Ejecutar la aplicación

```bash
dotnet run
```

La aplicación estará disponible en `https://localhost:5001` o `http://localhost:5000` (según la configuración).

---

## 📦 Estructura del Proyecto

```
ProyectoInformatico/
├── Controllers/          # Controladores MVC
│   ├── AdminController.cs
│   ├── CitaController.cs
│   ├── DiagnosticoController.cs
│   ├── EspecialistaController.cs
│   ├── HomeController.cs
│   ├── PacienteController.cs
│   └── PdfController.cs
├── Models/               # Modelos de datos
│   ├── Admin.cs
│   ├── Cita.cs
│   ├── Diagnostico.cs
│   ├── Especialista.cs
│   ├── ImagenRadiologica.cs
│   ├── Paciente.cs
│   └── VideoEcografia.cs
├── Services/             # Lógica de negocio
│   ├── AdminService.cs
│   ├── BlobStorageService.cs
│   ├── CitaService.cs
│   ├── DiagnosticoService.cs
│   ├── EspecialistaService.cs
│   ├── ImagenRadiologicaService.cs
│   ├── PacienteService.cs
│   └── VideoEcografiaService.cs
├── DTOs/                 # Objetos de transferencia de datos
├── Views/                # Vistas Razor
│   ├── Admin/
│   ├── Especialista/
│   ├── Home/
│   ├── Paciente/
│   └── Shared/
├── wwwroot/              # Archivos estáticos (CSS, JS, imágenes)
├── Configurations/       # Configuraciones adicionales
├── ArchivosTemporales/   # Directorio para archivos temporales
├── Properties/           # Configuración del proyecto
├── Program.cs            # Punto de entrada de la aplicación
├── appsettings.json      # Configuración de la aplicación
└── ProyectoInformatico.csproj
```

---

## 🔑 Roles y Permisos

El sistema implementa tres roles principales con diferentes niveles de acceso:

| Rol | Permisos |
|-----|----------|
| **Administrador** | Gestión completa del sistema, administración de especialistas, reportes |
| **Especialista** | Creación de diagnósticos, gestión de citas, subida de videos e imágenes |
| **Paciente** | Visualización de diagnósticos, solicitud de citas, descarga de recursos |

---

## 🎥 Funcionalidades Clave

### Conversión de Videos

El sistema convierte automáticamente videos ecográficos del formato AVI a MP4 utilizando la API de Zamzar, permitiendo una mejor compatibilidad y compartición con los pacientes.

### Procesamiento DICOM

Utiliza la librería fo-dicom para procesar y gestionar imágenes radiológicas en formato DICOM, estándar internacional en el ámbito médico.

### Generación de PDFs

Crea diagnósticos en formato PDF personalizados que incluyen:
- Información del paciente
- Conclusiones del especialista
- Imágenes radiológicas
- Videos ecográficos convertidos

### Notificaciones por Email

Envía automáticamente diagnósticos completos a los pacientes por correo electrónico, incluyendo:
- PDF del diagnóstico
- Videos ecográficos en formato MP4
- Imágenes radiológicas adjuntas

---

## 🔐 Seguridad

- Autenticación basada en cookies con expiración configurable
- Autorización basada en roles (Admin, Doctor, Paciente)
- Encriptación de contraseñas con BCrypt
- Políticas de acceso denegado configuradas
- Validación de archivos y tipos MIME

---

## 📊 Contexto Médico

### Ecografía 4D

La ecografía 4D es una técnica de imagenología que permite la visualización tridimensional en tiempo real del feto con movimiento. Se utiliza para:
- Observar el desarrollo fetal
- Identificar características fetales
- Descartar ciertas patologías

### Gestión de Diagnósticos

Durante una sesión de análisis se produce:
- Un conjunto de videos ecográficos
- Una interpretación o diagnóstico realizado por radiólogo y/o ginecólogo
- Imágenes radiológicas en formato DICOM

En escenarios que involucran patologías fetales o condiciones que podrían poner en riesgo el proceso de parto, el sistema permite diferenciar el personal de salud que interpreta las imágenes.

---

## 📝 Configuración de Desarrollo

### Variables de Entorno

Para desarrollo local, puedes usar `appsettings.Development.json`:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Debug",
      "Microsoft.AspNetCore": "Information"
    }
  }
}
```

### Directorio de Archivos Temporales

El sistema crea automáticamente el directorio `ArchivosTemporales/` si no existe, utilizado para el procesamiento temporal de videos e imágenes antes de su almacenamiento en Azure.

---

## 🧪 Testing

Para ejecutar pruebas (si están configuradas):

```bash
dotnet test
```

---

## 📧 Contacto y Soporte

Para más información sobre el proyecto o reportar problemas, contacta al equipo de desarrollo.

---

## 👥 Autores

- Alfonso Miguel Hernández - [@FonzHdz](https://github.com/FonzHdz)
- Ricardo Stiven Hernández - [@Stivenhdez2308](https://github.com/Stivenhdez2308)
- Juan Sebastian Valderrama - [@Xunni1e](https://github.com/Xunni1e)

---

## 📄 Licencia

Este proyecto es parte de un proyecto académico/informático.

---

<div align="center">

  <sub>Proyecto para la materia Proyecto Informático 1</sub>

</div>

