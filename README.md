# Workflow de triage de alertas de autenticación (SOC universitario)

Python + LangChain. Flujo: entrada → guardrails/seudonimización → agente (LLM) → validación de esquema → enrutado → auditoría.

## Uso
```bash
pip install -r requirements.txt
PYTHONPATH=. python run_demo.py            # demo con modelo simulado
PYTHONPATH=. python -m pytest -q tests     # 6 pruebas unitarias
PYTHONPATH=. python evaluate.py            # E1-E5 -> out/resultados.json
PYTHONPATH=. python make_figs.py           # figuras del documento
# con modelo real (requiere OPENAI_API_KEY en el entorno):
PYTHONPATH=. python run_demo.py --live
PYTHONPATH=. python evaluate.py --live     # añade out/resultados.json -> "live" (completa la fila pendiente de la Tabla V)
```
El modelo simulado valida el flujo; no mide la calidad de un LLM real. Datos 100 % sintéticos (semilla 7).
# workflow_soc_triage
