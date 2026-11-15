# [NOMBRE_DEL_SERVICIO] - Servidor de [Función Principal]

Breve descripción del servicio (1-2 líneas). Qué problema resuelve en tu infraestructura o red local.

---

## 🛠️ Hardware Resources 
Detalle del aprovisionamiento asignado en el clúster de Proxmox VE.

| Parámetro        | Configuración                  | Justificación Técnica                                               |
| :--------------- | :----------------------------- | :------------------------------------------------------------------ |
| **ID LXC**       | `CT XXX`                       | Identificador único en el nodo.                                     |
| **Architecture** | Unprivileged (No Privilegiado) | Aislamiento de seguridad contra escalada de privilegios al host.    |
| **SO **          | Debian 12 / Ubuntu 24.04       | Estabilidad, soporte a largo plazo y bajo consumo de recursos.      |
| **vCPU**         | X Core(s)                      | Ajustado según la carga estimada de cómputo del servicio.           |
| **RAM**          | XXX MB / GB                    | Optimización de memoria para evitar sobreasignación en el host.     |
| **Storage**      | XX GB (SSD/HDD)                | Espacio mínimo requerido más margen para logs y datos persistentes. |

---

## 🌐 Network Configuration
Detalles de conectividad y direccionamiento del contenedor.

* **Interface:** `eth0` puenteada a `vmbr0` (o la VLAN correspondiente).
* **IP Address:** `192.168.X.X/24` (IP Estática asignada por Proxmox / Reserva DHCP).
* **(Gateway:** `192.168.X.1`
* **Exposed Ports:**
  * `XX` (TCP/UDP) - Propósito del puerto (ej: Panel Web, API, Tráfico DNS).

---

## 🚀 Despliegue e Infraestructura como Código (IaC)
Pasos exactos o scripts utilizados para la creación del contenedor.

### Creación del LXC (Proxmox CLI)
```bash
# Comando utilizado para provisionar el contenedor desde la terminal de Proxmox
pct create XXX local:vztmpl/debian-12-...
```

### Configuración del Servicio (Provisionamiento)
```bash
# Pasos de instalación dentro del contenedor (scripts, ansible, o comandos manuales)
apt update && apt install -y servicio
```

---

## 🔐 Security and Hardening
Medidas implementadas para mitigar riesgos y proteger el entorno.

* **Firewall de Proxmox:** Activado a nivel de interfaz IP con reglas estrictas (Drop por defecto, Allow solo puertos específicos).
* **Acceso SSH:** Desactivado para el usuario `root` / Permitido únicamente mediante llaves SSH.
* **Características LXC (Features):** Deshabilitadas (NFS, SMB, FUSE, Nesting) para mantener la superficie de ataque al mínimo, excepto si el servicio lo requiere.

---

## 💾 Backups and Manteinance 
Estrategia para garantizar la continuidad del negocio / disponibilidad del servicio.

* **Backup:** Configurado en **Proxmox Backup Server (PBS)** / VZDump.
  * **Frecuency:** Diaria / Semanal.
  * **Retention:** Últimas X copias de seguridad.
  * **Mode:** Snapshot (sin interrupción del servicio).
* **Updates:** Documentar la rutina de mantenimiento (ej: Script cron para `apt update && apt upgrade -y`).
* **Monitoring:** Integración con herramientas de telemetría (ej: Prometheus/Grafana, Uptime Kuma o alertas de salud).
