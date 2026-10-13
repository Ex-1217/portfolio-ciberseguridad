# Portfolio de Ciberseguridad — Carlos López Urbaneja

Proyectos **propios**, montados y probados de principio a fin en un laboratorio casero: detección de ataques con un SIEM, triaje automático de alertas con tickets e IA, y agentes de IA diseñados con criterios de seguridad.

Cada proyecto se ha probado con un caso real y está documentado con una guía completa y una guía rápida.

📄 **[Portfolio completo en PDF](Portfolio_Carlos_Lopez_Urbaneja.pdf)**

---

## 🛡️ Laboratorio SOC: Wazuh + n8n + Jira con IA

Laboratorio en máquinas virtuales (red aislada) donde **Wazuh** vigila Windows 10 y Ubuntu, con Metasploitable como objetivo de práctica. Las alertas graves (nivel ≥ 10) pasan a **n8n**, que abre un ticket en **Jira**; una **IA** lo analiza y recomienda cerrar o escalar. La decisión final es del analista.

**Prueba real:** 9 inicios de sesión fallidos en Windows → alerta 60204 (MITRE T1110, fuerza bruta) → ticket en Jira con el análisis de la IA como comentario.

**Herramientas:** VirtualBox · Kali Linux · Wazuh 4.14.8 · Windows 10 + Sysmon · Ubuntu · Metasploitable 2 · n8n (Docker) · Jira Cloud · Groq

![Laboratorio SOC](Laboratorio_SOC.png)

---

## 📬 Agentes de correo con IA: Gmail, Outlook y Hotmail

Cada día revisan las tres cuentas, clasifican el correo nuevo (publicidad, requiere respuesta, sospechoso) y dejan las respuestas preparadas como borrador. **Nunca envían ni borran: decido yo.**

**Prueba real:** correo trampa con instrucciones ocultas para la IA → marcado como sospechoso y sin respuesta (defensa ante *prompt injection*).

**Herramientas:** n8n (Docker) · Gemini 2.5 Flash · Gmail API (OAuth) · Microsoft Graph · Entra ID

![Agentes de correo](Agentes_correo.png)

---

## 🤖 Asistente personal: pregunta a tus PDF

Lee los documentos de una carpeta de Google Drive y responde en un chat citando el documento. Si algo no está, responde «No localizado»: **no inventa** (sistema RAG con control de alucinaciones).

**Herramientas:** n8n (Docker) · Google Drive · Gemini · Embeddings · Vector Store

![Asistente personal](Asistente_personal.png)

---

## 🎓 Formación

- **Fundación GoodJob · Programa IMPACT.** Proyecto final: asistente de IA de cumplimiento normativo (GDPR, ISO 27001:2022 y ENS) para una empresa ficticia.
- **Itinerarios autodidactas** (facilitados por la fundación): Analista SOC Junior (Blue Team) y Auditor de Accesibilidad.

---

## 🧭 Cómo trabajo

- **Pruebo de principio a fin:** cada proyecto se da por terminado solo cuando funciona con un caso real.
- **Documento todo:** guía completa y guía rápida, con los problemas encontrados y su solución.
- **Seguridad desde el diseño:** red aislada, credenciales fuera de los flujos, mínimo privilegio y MFA.
- **La IA ayuda, yo decido:** la IA analiza y propone; las decisiones las toma una persona.
