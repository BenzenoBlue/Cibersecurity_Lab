

---

### **Resultado visual**  
El diagrama generado se verá así (GitHub renderiza automáticamente Mermaid):  

![Diagrama de Red]
![Untitled diagram-2025-02-09-194320](https://github.com/user-attachments/assets/333a665b-58a3-42ba-b9d1-775930f3ff72)

---

### **Explicación detallada**  
1. **Nodos y conexiones**:  
   - `Kali Linux` se conecta a `Windows 10` y `Ubuntu Server` mediante la red aislada.  
   - `Ubuntu Server` despliega herramientas clave para el Blue Team.  

2. **Estilos**:  
   - Colores diferenciados para cada tipo de nodo (rojo=atacante, azul=endpoint, verde=servidor seguro).  
   - Puedes personalizar los colores modificando los valores `fill` en `style`.  

3. **IPs**:  
   - Si has asignado IPs estáticas en tu lab, actualiza las direcciones en la sección **Componentes Clave**.  

---

### **Versión alternativa con más detalle (opcional)**  
Si quieres incluir direcciones IP y flujos de tráfico:  
```markdown
```mermaid
graph TB
    subgraph Red Aislada [🛡️ Red Virtual (192.168.56.0/24)]
        A[Kali Linux\n192.168.56.10] -->|Escaneo/ataques| B[Windows 10\n192.168.56.20]
        A -->|Envía tráfico malicioso| C[Ubuntu Server\n192.168.56.30]
        C -->|Monitorea logs| D[(Splunk\nSIEM)]
        C -->|Analiza tráfico| E[(Suricata\nIDS)]
        C -->|Captura paquetes| F[(Wireshark)]
    end

    style A fill:#ff9999,stroke:#333
    style B fill:#99ccff,stroke:#333
    style C fill:#99ff99,stroke:#333
