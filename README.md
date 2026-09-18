Servidor web seguro con Apache en Ubuntu Server 24.04

Proyecto final del ciclo de Administración de Sistemas Informáticos en Red (ASIR): despliegue de un servidor web funcional y seguro sobre Ubuntu Server 24.04, con cifrado HTTPS mediante certificados SSL/TLS autofirmados y protegido con un firewall configurado con iptables.

Objetivo

Poner en práctica conocimientos de administración de servidores Linux, configuración de servicios de red, seguridad y firewalls, demostrando que es posible implementar una solución web segura sin depender de servicios de terceros ni asumir costes adicionales — una alternativa válida para entornos de desarrollo, centros educativos o pequeñas empresas.

Arquitectura
2 máquinas virtuales en VMware: un servidor (Ubuntu Server 24.04) y un cliente (Ubuntu 24.04 Desktop), comunicados mediante un adaptador de red interna, con el servidor además conectado a internet vía adaptador puente.
IP estática en el servidor; el cliente obtiene IP dinámica mediante un DHCP propio.
Habilidades demostradas
Servidor web: instalación y configuración de Apache2, con Virtual Hosts independientes para HTTP (redirigido a HTTPS) y HTTPS.
Cifrado HTTPS: generación de certificados SSL/TLS autofirmados (RSA 2048 bits) y configuración de Apache para forzar TLS 1.3.
Cabeceras de seguridad: Strict-Transport-Security (HSTS con preload), X-Content-Type-Options: nosniff y X-Frame-Options: DENY, para mitigar downgrade a HTTP, sniffing de contenido y clickjacking.
DNS y DHCP propios: implementación con dnsmasq, incluyendo resolución directa e inversa del dominio, registro de logs y asignación dinámica de IP al cliente.
Firewall (iptables): política por defecto restrictiva (DROP en INPUT/FORWARD), permitiendo únicamente los puertos necesarios (22 SSH, 80 HTTP, 443 HTTPS, 53 DNS) y reglas persistentes con iptables-persistent.
Gestión de permisos: aplicación de permisos diferenciados para archivos y directorios con find (en lugar de chmod global) y propietario www-data para el contenido servido por Apache.
Verificación y pruebas: comprobación del firewall con nmap, validación del certificado y desarrollo de una página de prueba en HTML + PHP para confirmar el funcionamiento extremo a extremo.
Herramientas y tecnologías

Ubuntu Server 24.04 · Apache2 · OpenSSL · dnsmasq (DNS + DHCP) · iptables / iptables-persistent · nmap · netplan · PHP · VMware

Fases del proyecto
Configuración de adaptadores de red y máquinas virtuales
Instalación y configuración inicial de Ubuntu Server 24.04
Servidor DNS y DHCP con dnsmasq
Instalación y configuración de Apache (Virtual Hosts)
Certificados SSL/TLS y HTTPS
Firewall con iptables
Página web de prueba (HTML + PHP)
Documentación completa

La memoria completa del proyecto, con capturas de pantalla paso a paso de cada fase, está disponible en Proyecto_Apache_Ubuntu_Server_24.04.pdf (ajusta el nombre/enlace según el archivo que subas).
