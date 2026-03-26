<img width="994" height="1219" alt="image" src="https://github.com/user-attachments/assets/4f5d6918-4de3-4e3f-8d21-aba7d9f9ca35" /><img width="844" height="1244" alt="image" src="https://github.com/user-attachments/assets/82f01e46-10bc-49b4-8bfb-a0bc17b1700d" /># AZ-104 - Laboratorio 05: Implementar conectividad entre sitios

## 📌 Descripción

En este laboratorio se explora la comunicación entre redes virtuales en Azure.  
Se implementa:

- Peering de redes virtuales 
- Pruebas de conectividad entre máquinas virtuales 
- Creación de rutas personalizadas 

---

## 🏗️ Diagrama de arquitectura

<img ancho="1169" alta="469" alt="imagen" src="https://github.com/user-attachments/assets/1baa83ca-109c-4a0f-a30d-55e9fb954cc7" />



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

<img widthSubiendo imagen.png…![ altura="1078" alt="imagen" src="https://github.com/user-attachments/assets/07430063-341a-424c-826c-6d5a56c0c86d" />

---

## 🔹 Paso 2: Crea la primera mañana virtual

Vas a crear la VM de servicios centrales.

1. Busca **Máquinas virtuales** y entra. 
2. Pulsa en **Crear → Máquina virtual**

### 🧾 Configuración - Pestaña *Conceptos básicos*

- **Grupo de recursos:** az104-rg5 
- **Nombre de la mañana virtual:** Servicios básicosVM 
- **Región:** Este de Estados Unidos 
- **Opțiuni de disponibilidad:** No se requiere redundancia de infraestructura 
- **Tipo de seguridad:** Estándar 
- **Imagen:** Centro de datos de Windows Server 2025: x64 Gen2 
- **Tamaño:** Estandar_D2s_v3 
- **Nombre de usuario:** administrador local 
- **Contraseña:** (una contraseña completa) 
- **Puertos públicos entrantes:** Ninguno 

![Subiendo imagen.png…]()


Pulsa **Siguiente: Discotecas**

---

### 💽 Pestaña *Discotecas*

- Deja la configuración por defecto

![Subiendo imagen.png…]()

- Pulsa **Siguiente: Redes**

---

### 🌐 Pestaña *Redes*

En **Rojo virtual**, pulsa **Crear nuevo** y configuración:

- **Nombre:** Servicios básicosVnet 
- **Rango de direcciones:** 10.0.0.0/16 

#### Subred:

- **Nombre de la subred:** Núcleo 
- **Rango de direcciones de subred:** 10.0.0.0/24 

Pulsa **OK**

---

### 📊 Pestaña *Monitoreo*

- **Diagnóstico de arreglo:** Deshabilitar 

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
