<img ancho="1169" alta="469" alt="imagen" src="https://github.com/user-attachments/assets/1baa83ca-109c-4a0f-a30d-55e9fb954cc7" /># AZ-104 - Laboratorio 05: Implementar conectividad entre sitios

## 📌 Descripción

En este laboratorio se explora la comunicación entre redes virtuales en Azure.  
Se implementa:

- Peering de redes virtuales 
- Pruebas de conectividad entre máquinas virtuales 
- Creación de rutas personalizadas 

---

## 🏗️ Diagrama de arquitectura

![Subiendo imagen.png…]()


> 📍 Nota: Añade la imagen al repositorio con el nombre `arquitectura.png`.

---

## 🎯 Objetivos del laboratorio

- Crear máquinas virtuales en diferentes redes virtuales 
- Configurar conectividad entre VNets 
- Validar conectividad con herramientas de Azure 
- Implementar rutas personalizadas 

---

## 🧪 Tareas del laboratorio

| Tarea | Descripción |
|------|------------|
| Tarea 1 | Crear VM en Red Core |
| Tarea 2 | Crear VM en rojo Fabricación |
| Tarea 3 | Probar conectividad con Network Watcher |
| Tarea 4 | Configuración de peering entre VNets |
| Tarea 5 | Probar conectividad con PowerShell |
| Tarea 6 | Crear ruta personalizada |

---

# 🚀 Implementación paso a paso

## 🔹 Paso 1: Entra al portal de Azure

Abre el navegador y entra en:

https://portal.azure.com

Inicio sesión con tu cuenta.

---

## 🔹 Paso 2: Crea la primera mañana virtual

Vas a crear la VM de servicios centrales.

1. Busca **Máquinas virtuales** y entra. 
2. Pulsa en **Crear → Máquina virtual**

### 🧾 Configuración - Pestaña *Conceptos básicos*

- **Grupo de recursos:** az104-rg5 
- **Nombre de la máquina virtual:** Servicios básicosVM 
- **Región:** Este de Estados Unidos 
- **Opțiuni de disponibilitate:** No se requiere redundancia de infraestructura 
- **Tipo de seguridad:** Estándar 
- **Imagen:** Centro de datos de Windows Server 2025: x64 Gen2 
- **Tamaño:** Estándar_D2s_v3 
- **Nombre de usuario:** administrador local 
- **Contraseña:** (una contraseña completa) 
- **Puertos públicos entrantes:** Ninguno 

Pulsa **Siguiente: Discos**

---

### 💽 Pestaña *Discos*

- Deja la configuración por defecto 
- Pulsa **Siguiente: Redes**

---

### 🌐 Pestaña *Redes*

En **Red virtual**, pulsa **Crear nuevo** y configuración:

- **Nombre:** Servicios básicosVnet 
- **Rango de direcciones:** 10.0.0.0/16 

#### Subred:

- **Nombre de la subred:** Núcleo 
- **Rango de direcciones de subred:** 10.0.0.0/24 

Pulsa **OK**

---

### 📊 Pestaña *Monitoreo*

- **Diagnóstico de arranque:** Deshabilitar 

---

### ✅ Finalizar

Pulsa:

Revisar + crear → Crear

---

## 📌 Próximos pasos

- Crear la VM de Manufactura 
- Configurar el peering de VNet 
- Probar conectividad entre máquinas 
- Implementar rutas personalizadas 
