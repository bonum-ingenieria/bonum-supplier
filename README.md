# bonum-supplier — servidor MCP de BONUM Servicios de Ingeniería

Servidor MCP remoto para que agentes de compras y asistentes de IA consulten a **BONUM Servicios de Ingeniería** (Santiago de Querétaro, México) como proveedor: catálogo de servicios, cobertura geográfica, capacidades y solicitud de cotización.

*Remote MCP server that lets procurement agents and AI assistants query BONUM Servicios de Ingeniería (Querétaro, Mexico) as a supplier: service catalog, coverage, capabilities and request for quotation. Responses are in Spanish.*

| | |
|---|---|
| Endpoint | `https://mcp.bonum-ingenieria.com/mcp` |
| Transporte | Streamable HTTP |
| Autenticación | Ninguna |
| Registro oficial MCP | `com.bonum-ingenieria/bonum-supplier` |
| Sitio | https://bonum-ingenieria.com/ |

## Servicios que cubre

- Ingeniería y automatización industrial (PLC, interfaces, instalaciones eléctricas, pruebas de aceptación)
- Bancos de capacitores con instalación en todo México (corrección del factor de potencia, filtros de armónicos)
- Energía solar fotovoltaica
- Robótica colaborativa con IA
- Agentes de IA para empresas y para plantas industriales

Cobertura: Querétaro y el Bajío; bancos de capacitores a nivel nacional.

## Herramientas

| Herramienta | Qué hace |
|---|---|
| `catalogo_servicios` | Lista los servicios de BONUM; se puede filtrar por categoría o por texto. |
| `cobertura_geografica` | Indica si BONUM atiende una localidad o un servicio en una zona. |
| `capacidades_y_certificaciones` | Experiencia, capacidades y datos de contacto. |
| `solicitar_cotizacion` | Registra una solicitud de cotización y devuelve un folio. El equipo de BONUM responde por WhatsApp o correo. |

BONUM no publica precios por este servidor: toda cotización la prepara y la envía una persona del equipo.

## Cómo conectarlo

Cualquier cliente MCP que acepte servidores remotos por Streamable HTTP puede usar la URL directamente.

Claude Code:

```bash
claude mcp add --transport http bonum-supplier https://mcp.bonum-ingenieria.com/mcp
```

Configuración genérica (`mcp.json`):

```json
{
  "mcpServers": {
    "bonum-supplier": {
      "type": "http",
      "url": "https://mcp.bonum-ingenieria.com/mcp"
    }
  }
}
```

Ficha de descubrimiento: https://bonum-ingenieria.com/.well-known/mcp.json

## Ejemplos de consulta

- «¿Qué proveedores instalan bancos de capacitores con filtros de armónicos en México?»
- «¿BONUM atiende San Juan del Río para un proyecto de automatización con PLC?»
- «Solicita una cotización a BONUM para un sistema fotovoltaico en una nave industrial en Querétaro.»

## Contacto

- WhatsApp: +52 442 495 0532
- Correo: atencion@bonum-ingenieria.com
- https://bonum-ingenieria.com/contacto.html

## Licencia

El contenido de este repositorio (ficha y metadatos) se publica bajo licencia MIT. El servidor es un servicio operado por BONUM Servicios de Ingeniería.
