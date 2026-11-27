# Agente Inteligente de RRHH - LLM y RAG

Asistente de recursos humanos que recupera información relevante de documentos y genera respuestas contextualizadas mediante modelos de lenguaje. El proyecto aborda consultas frecuentes sobre vacaciones, permisos, beneficios y procedimientos internos, mostrando las fuentes utilizadas.

## Funcionalidades

- Consultas en lenguaje natural mediante consola.
- Fragmentación de documentos y generación de embeddings.
- Recuperación semántica con FAISS.
- Generación de respuestas mediante un LLM y contexto documental.
- Identificación de fuentes y orientación ante información insuficiente.

## Arquitectura

| Etapa | Responsabilidad |
| --- | --- |
| Ingesta | Lectura y fragmentación de documentos TXT. |
| Indexación | Embeddings e índice vectorial FAISS en memoria. |
| Recuperación | Selección de fragmentos relevantes para la consulta. |
| Generación | LangChain y GitHub Models. |
| Presentación | Respuesta y referencias en consola. |

## Tecnologías

Python, LangChain, FAISS, GitHub Models, GPT-4o-mini, embeddings, Git y GitHub.

## Estructura

- `app.py`: interfaz de consola.
- `src/`: carga documental, indexación y lógica RAG.
- `data/`: documentación ficticia de ejemplo.
- `requirements.txt`: dependencias.
- `.env.example`: configuración sin credenciales.

## Ejecución local

Requiere Python 3.11 o una versión compatible con las dependencias, acceso a GitHub Models y un token propio con permisos mínimos necesarios.

```cmd
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
copy .env.example .env
```

Completar `.env` con el token propio. Los modelos y el endpoint son configurables; su disponibilidad depende del proveedor.

```cmd
.venv\Scripts\python app.py
```

Ejemplos: ¿Cómo solicito vacaciones? ¿Qué beneficios existen? ¿Cómo solicito un permiso?

## Seguridad y alcance

La versión de portafolio contiene documentos ficticios y no incorpora credenciales, índices serializados ni registros personales. El índice se genera en memoria para evitar la deserialización de archivos pickle. El procesamiento con modelos remotos envía fragmentos y consultas al proveedor: no introducir información confidencial. Las respuestas pueden contener errores y no constituyen asesoría laboral o legal.

Proyecto desarrollado en equipo en un contexto formativo. Adaptación de portafolio con asistencia de IA. La ejecución contra los modelos remotos requiere validación con credenciales propias. La redistribución está sujeta a los derechos correspondientes.
