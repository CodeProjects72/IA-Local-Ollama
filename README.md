# Ollama · Instalación y configuración

> Instalación de Ollama en Linux y configuración básica para ejecutar modelos de lenguaje localmente.

---

## 01 · Instalación

Instala Ollama mediante el script oficial:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

---

## 02 · Instalación manual del paquete ROCm

Si necesitas la versión para AMD/ROCm, descarga y descomprime el paquete directamente en `/usr`:

```bash
curl -fsSL https://ollama.com/download/ollama-linux-amd64-rocm.tar.zst | sudo tar --zstd -x -C /usr
```

---

## 03 · Iniciar el servicio

Inicia el servicio de Ollama:

```bash
sudo systemctl start ollama
```

Comprueba su estado:

```bash
sudo systemctl status ollama
```

---

## 04 · Ejecutar un modelo

Para descargar y ejecutar `llama3.2`:

```bash
ollama run llama3.2
```

La primera ejecución descargará automáticamente el modelo si todavía no está instalado.

---

## 05 · Comandos básicos

Comprobar la versión instalada:

```bash
ollama --version
```

Ver los modelos instalados:

```bash
ollama list
```

Descargar un modelo:

```bash
ollama pull llama3.2
```

Eliminar un modelo:

```bash
ollama rm llama3.2
```

---

## 06 · Servicio automático

Para iniciar Ollama automáticamente al arrancar el sistema:

```bash
sudo systemctl enable ollama
```

Puedes habilitarlo e iniciarlo al mismo tiempo:

```bash
sudo systemctl enable --now ollama
```

---

## 07 · Verificación

Comprueba que el servicio está funcionando:

```bash
systemctl is-active ollama
```

Y verifica que Ollama responde correctamente:

```bash
ollama list
```

---

## Resumen

```text
Ollama
├── Instalación
├── ROCm / AMD
├── Servicio systemd
├── Modelos
└── Verificación
```
