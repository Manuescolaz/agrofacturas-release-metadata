# Agrofacturas — metadatos de versiones

**ESTE REPOSITORIO CONTIENE ÚNICAMENTE METADATOS SANEADOS DE LAS VERSIONES PUBLICADAS DE AGROFACTURAS.**

No contiene, y no puede contener:

- código fuente del producto;
- paquetes de instalación ni actualizaciones (`.zip`, `.exe`, `.dmg`, `.msi`);
- enlaces de descarga a artefactos privados;
- bases de datos, configuración, registros ni copias de seguridad;
- credenciales, claves de API ni tokens;
- datos personales, identificadores fiscales ni direcciones de correo;
- rutas de red o de disco de ninguna instalación;
- marca, logotipos ni plantillas de ningún cliente.

El código de Agrofacturas y sus paquetes de instalación son **privados** y se
distribuyen por un canal aparte. Este repositorio existe sólo para que la
pantalla «Historial de cambios» del programa pueda consultar qué versiones hay
publicadas y qué cambió en cada una, **sin necesidad de credenciales**.

## Contenido

| Archivo | Qué es |
|---|---|
| `releases.json` | Lista de versiones publicadas: número, fecha, título y notas. |
| `README.md` | Este archivo. |

## `releases.json`

```json
{
  "schema_version": 1,
  "producto": "agrofacturas",
  "generado": "2026-09-28T00:00:00Z",
  "latest": "1.1.1",
  "releases": [
    {
      "version": "1.1.1",
      "published_at": "2026-09-21T10:21:07Z",
      "title": "Versión 1.1.1",
      "notes": ["## Nuevo", "- …"]
    }
  ]
}
```

| Campo | Significado |
|---|---|
| `schema_version` | Versión del formato. Un cliente que no la entienda debe rechazar el documento en vez de interpretarlo a medias. |
| `latest` | Número de la versión más reciente de la lista. **Informativo**: no da acceso a ningún paquete. |
| `releases` | Versiones ordenadas de más reciente a más antigua. |
| `releases[].version` | `X.Y.Z`. |
| `releases[].published_at` | Fecha de publicación, en ISO 8601 (UTC). |
| `releases[].title` | Título de la versión, si tiene uno distinto del número. |
| `releases[].notes` | Notas de la versión, una línea por elemento. Admiten `## Encabezado`, `- viñeta` y `**negrita**`. |

El formato es **extensible**: un cliente debe ignorar los campos que no conozca.

## Cómo se genera

Las notas se escriben **una sola vez**, al publicar la versión en el repositorio
privado de releases. De ahí se derivan automáticamente los metadatos de aquí,
saneándolos y comprobándolos antes de subirlos. No se mantienen dos copias a
mano.

El proceso se niega a publicar si encuentra algo que exija revisión humana.

## Aviso

Este repositorio es público por diseño, pero **no es una invitación a
redistribuir el producto**. Agrofacturas es software propietario. Copyright (c)
2024-2026 Manuel Escola. Todos los derechos reservados.
