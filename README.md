# AZ-104 - Laboratorio 05: Implementar conectividad entre sitios

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
| Tarea 1 | Crear VM en una Red Virtual |
| Tarea 2 | Crear VM en otra Red Virtual |
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

<img widt alta="1078" alt="imagen" src="https://github.com/user-attachments/assets/07430063-341a-424c-826c-6d5a56c0c86d" />

---

## 🔹 Paso 2: Crea la primera mañana virtual

Vas a crear la VM de servicios centrales.

1. Busca **Máquinas virtuales** y entra. 
2. Pulsa en **Crear → Máquina virtual**

### 🧾 Configuración - Pestaña *Conceptos básicos*

- **Grupo de recursos:** az104-rg5 
- **Nombre de la mañana virtual:** CoreServicesVM
- **Región:** La que te permita tu subcirpcion 
- **Opțiuni de disponibilidad:** No se requiere redundancia de infraestructura 
- **Tipo de seguridad:** Estándar 
- **Imagen:** Centro de datos de Windows Server 2025: x64 Gen2 
- **Tamaño:** Standard_B2ats_v2 
- **Nombre de usuario:** admin 
- **Contraseña:** (una contraseña completa) 
- **Puertos públicos entrantes:** Ninguno 

<img width="617" height="1213" alt="image" src="https://github.com/user-attachments/assets/ff23fa23-80ba-4bdc-bae2-3f4de357ddf1" />



Pulsa **Siguiente: Discos**

---

### 💽 Pestaña *Discos*

- Deja la configuración por defecto

<img ancho="994" alta="1219" alt="imagen" src="https://github.com/user-attachments/assets/4f5d6918-4de3-4e3f-8d21-aba7d9f9ca35" />

- Pulsa **Siguiente: Redes**

---

### 🌐 Pestaña *Redes*

En **Red Virtual**, pulsa **Crear nuevo** y configuración:

- **Nombre:** CoreServicesVnet 
- **Rango de direcciones:** 10.0.0.0/16 

#### Subred:

- **Nombre de la subred:** Core
- **Rango de direcciones de subred:** 10.0.0.0/24 

Pulsa **OK**

<img width="3382" height="1251" alt="image" src="https://github.com/user-attachments/assets/f1f71442-7e6d-4d34-a34a-b4b4eb4c1771" />

---

### 📊 Pestaña *Supervision*

- **Diagnósticos de arranque:** Deshabilitar
  
<img width="1046" height="1253" alt="image" src="https://github.com/user-attachments/assets/dbcbe439-711f-47a8-8c78-a82ee27e469a" />

---

### ✅ Finalizar

Pulsa:

Revisar + crear → Crear

<img width="771" height="127" alt="image" src="https://github.com/user-attachments/assets/1f51c892-bf6d-4670-adc1-65e954a3085c" />

## Asi deberia quedar en la pestaña de revision:

<img width="812" height="1255" alt="image" src="https://github.com/user-attachments/assets/32bfbdb1-f828-4936-9214-73ec8db7767a" />


---


## 🔹 Paso 2: Crear La segunda Maquina virtual

### 🧾 Configuración - Pestaña *Conceptos básicos*

- **Grupo de recursos:** az104-rg5 
- **Nombre de la mañana virtual:** ManufacturingVM
- **Región:** Distinta region a la primer amaquina virtual 
- **Opțiuni de disponibilidad:** No se requiere redundancia de infraestructura 
- **Tipo de seguridad:** Estándar 
- **Imagen:** Centro de datos de Windows Server 2025: x64 Gen2 
- **Tamaño:** Standard_B2ats_v2 
- **Nombre de usuario:** administrador
- **Contraseña:** (una contraseña completa) 
- **Puertos públicos entrantes:** Ninguno 

<img width="736" height="1206" alt="image" src="https://github.com/user-attachments/assets/b86dbaf4-2982-4fb8-a489-593863529789" />

Pulsa **Siguiente: Discos**

### 💽 Pestaña *Discos*

- Deja la configuración por defecto

<img width="890" height="1184" alt="image" src="https://github.com/user-attachments/assets/2a3fa474-40f6-41c1-b60a-274b4996b844" />

- Pulsa **Siguiente: Redes**

---

### 🌐 Pestaña *Redes*

En **Red Virtual**, pulsa **Crear nuevo** y configuración:

- **Nombre:** ManufacturingVnet 
- **Rango de direcciones:** 172.16.0.0/16 

#### Subred:

- **Nombre de la subred:** Manufacturing
- **Rango de direcciones de subred:** 172.16.0.0/24 

Pulsa **OK**

<img width="3377" height="1239" alt="image" src="https://github.com/user-attachments/assets/2ed2a5db-d655-4c96-897d-47407cd060bc" />


---

### 📊 Pestaña *Supervision*

- **Diagnósticos de arranque:** Deshabilitar
  
<img width="1046" height="1253" alt="image" src="https://github.com/user-attachments/assets/dbcbe439-711f-47a8-8c78-a82ee27e469a" />

---

### ✅ Finalizar

Pulsa:

Revisar + crear → Crear

<img width="771" height="127" alt="image" src="https://github.com/user-attachments/assets/1f51c892-bf6d-4670-adc1-65e954a3085c" />

## Asi deberia quedar en la pestaña de revision:

<img width="943" height="1228" alt="image" src="https://github.com/user-attachments/assets/6a808a6b-6132-4b7e-8364-9bafcc7ee5b0" />



---


## 🔹 Tarea 3: Usar Network Watcher para probar la conexión

⚠️ **Asegúrate de que ambas máquinas virtuales estén desplegadas antes de continuar**

1. Busca **Network Watcher** en el portal de Azure  
2. Entra en **Connection troubleshoot**

<img width="1641" height="1227" alt="image" src="https://github.com/user-attachments/assets/b7241e0d-6f84-4f1b-b75e-163cb2e799f7" />


### ⚙️ Configuración

Configura los siguientes parámetros:

- **Tipo de Origen:** Maquina virtual 
- **Virtual machine:** CoreServicesVM  
- **Destino:** ManufacturingVM  
- **Virtual machine:** ManufacturingVM  
- **version de IP preferida:** Ambos  
- **Protocolo:** TCP  
- **Puerto de Destino:** 3389  
- **Source port:** (vacío)  
- **Diagnostic tests:** Deja el que esta por defecto 

Pulsa **Run diagnostic tests**

<img width="1661" height="1246" alt="image" src="https://github.com/user-attachments/assets/bb54c36c-e1bc-4ddb-bd1a-0ecad7de16dc" />


---

### 📊 Resultado esperado

- ❌ **Unreachable**

<img width="1134" height="461" alt="image" src="https://github.com/user-attachments/assets/844d3f2d-4eab-4c58-a517-61574f82ac6a" />


---

### 🧠 Explicación

✔️ Este resultado es correcto porque:

- Las máquinas están en **redes virtuales diferentes**  
- **No existe aún peering entre VNets**  
- No hay conectividad configurada entre ellas  

➡️ En la siguiente tarea se configurará el **VNet Peering** para permitir la comunicación.

---

## 🔹 Tarea 4: Configurar peering entre redes virtuales

1. Entra en **CoreServicesVnet**  
2. Ve a la sección **Emparejaminetos**  
3. Pulsa en **+ Agregar**

<img width="1645" height="1166" alt="image" src="https://github.com/user-attachments/assets/73a1b6da-4354-49a0-8694-1cab0c0c5478" />


### ⚙️ Configuración

Configura los siguientes parámetros:

#### 🔗 Resumen de la red virtual remota

- **Nombre del Emparejamiento:** ManufacturingVnet-to-CoreServicesVnet
- **Tipo de Emparejamiento:** Red Virtual 
- **Virtual network:** ManufacturingVnet  
- **Permitir 'ManufacturingVnet' para acceder a 'CoreServicesVnet:** seleccionado  
- **Permitir 'ManufacturingVnet' para recibir el tráfico reenviado desde 'CoreServicesVnet:** seleccionado  

---

#### 🔗 Resumen de la red virtual local
- **Nombre del Emparejamiento:** ManufacturingVnet-to-CoreServicesVnet
- **Tipo de Emparejamiento:** Red Virtual 
- **Red Virtual:** ManufacturingVnet  
- **Permitir 'CoreServicesVnet' para acceder a 'ManufacturingVne:** seleccionado  
- **Permitir 'CoreServicesVnet' para recibir el tráfico reenviado desde 'ManufacturingVnet:** seleccionado  
---

Pulsa **Agregar**
###Asi deberia quedar la Configuracion:

<img width="1185" height="1191" alt="image" src="https://github.com/user-attachments/assets/6e1a0fd9-c027-4a13-b174-e75d7bdafabe" />

---

### 📊 Verificación

Comprueba en ambas redes virtuales:

Para ello vualve a hacer la parte 3. Aqui te deberia salir que si hay conexion

- ✔️ **Estado:** Conectado  

<img width="1044" height="393" alt="image" src="https://github.com/user-attachments/assets/124133a9-2bb9-4168-839d-b62e59c9897a" />

---

### 🧠 Explicación

El **VNet Peering** permite que dos redes virtuales se comuniquen como si estuvieran en la misma red.

✔️ Ahora las máquinas virtuales podrán conectarse entre sí  
✔️ La comunicación es privada y dentro de la red de Azure  
