# Cybersecurity-Labs-Network-Security-MAC-Spoofing-
Laboratorio de Manipulación de Capa 2: MAC Spoofing Multiplataforma. Documentación técnica de suplantación de identidad de red en entornos virtualizados. Incluye procedimientos detallados para la modificación de direcciones físicas en Kali Linux (terminal/macchanger) y Windows (Technitium). Análisis de vulnerabilidades en filtros de red.
# Laboratorio de MAC Spoofing: Entornos Multiplataforma (Kali & Windows)

## 📌 Descripción
Este laboratorio práctico forma parte de mi formación en **Ingeniería en Computación (UNIR)**. El objetivo es demostrar la volatilidad de la identidad física (Capa 2 del Modelo OSI) mediante la técnica de MAC Spoofing en entornos virtualizados controlados.

---

## 🛠️ Entorno de Laboratorio
* **Hipervisor:** VirtualBox / VMware.
* **Sistemas Operativos:** - Kali Linux (Atacante/Auditor).
  - Windows 10/11 (Objetivo/Administración).
* **Configuración de Red:** Adaptador Puente (Bridged) + Modo Promiscuo (Allow All).
* **Seguridad:** Uso de Snapshots (Instantáneas) preventivas.

---

## 🚀 Fase 1: Kali Linux (Terminal & Macchanger)
En este entorno se validó la manipulación directa de la interfaz de red mediante comandos de consola.

### Comandos Utilizados:
1. **Desactivar interfaz:**
     sudo ifconfig eth0 down
2. **Cambio aleatorio con Macchanger:** 
     sudo macchanger -r eth0
3. **Cambio manual específico:**
     sudo ifconfig eth0 hw ether 00:11:22:33:44:55
4. **Reactivar y verificar:**
     sudo ifconfig eth0 up

---

### Fase 2: Windows (Technitium MAC Address Changer)
Se utilizó software especializado para interactuar con el Registro de Windows y enmascarar la dirección física de la NIC virtual.

## Procedimiento:
1. Selección del adaptador de red activo.
2. Generación de Random MAC Address con prefijos de fabricantes específicos (OUI).
3. Aplicación del cambio mediante la modificación del registro NetworkAddress.
4. Verificación en CMD:
    ipconfig /all

---

### Conclusiones Técnicas
El MAC Spoofing es una técnica eficaz para evadir filtros de seguridad basados únicamente en listas blancas de direcciones físicas.
La implementación en Windows requiere privilegios de administrador para modificar el registro, mientras que en Linux se opera a nivel de controlador de red (driver).
La importancia del Modo Puente en la VM es crítica para que el cambio sea visible por el Router/Gateway de la red local.

### Nota Legal y Ética
Este laboratorio se realizó con fines estrictamente educativos y bajo el consentimiento en un entorno privado. El uso de estas técnicas en redes ajenas sin autorización es ilegal.

Autor: Victor Manuel Sánchez Ramírez

Estudiante de Ingeniería Informática | CEO VMA Abogados
   
