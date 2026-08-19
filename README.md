# Performance Testing con JMeter

Suite completa de testing de rendimiento con Apache JMeter contra APIs públicas.

## Características

- **Load Test**: Prueba de carga con 50 usuarios
- **Stress Test**: Prueba de estrés con 200 usuarios
- **Spike Test**: Prueba de picos con 500 usuarios
- **Assertions**: Validación automática de respuestas
- **Reports**: Reportes detallados de rendimiento

## Requisitos

- Apache JMeter 5.6+ (`choco install jmeter`)

## Instalación

```bash
# Windows (Chocolatey)
choco install jmeter

# macOS (Homebrew)
brew install jmeter
```

## Ejecución

```bash
# Ejecutar desde línea de comandos
jmeter -n -t test-plans/load-test.jmx -l utils/load-results.jtl -e -o reports/load-report

# Ejecutar stress test
jmeter -n -t test-plans/stress-test.jmx -l utils/stress-results.jtl -e -o reports/stress-report

# Ejecutar spike test
jmeter -n -t test-plans/spike-test.jmx -l utils/spike-results.jtl -e -o reports/spike-report
```

## Ejecución con GUI

```bash
jmeter
```

Luego abrir el archivo `.jmx` correspondiente y ejecutar.

## Estructura

```
performance-testing-jmeter/
├── test-plans/
│   ├── load-test.jmx
│   ├── stress-test.jmx
│   └── spike-test.jmx
├── utils/
│   └── *.jtl (generated)
├── reports/
│   └── */ (generated)
└── README.md
```

## Configuración de tests

| Test | Usuarios | Ramp-up | Duración | Think Time |
|------|----------|---------|----------|------------|
| Load | 50 | 30s | 5m | 1s |
| Stress | 200 | 60s | 10m | 500ms |
| Spike | 500 | 10s | 2m | 100ms |

## Métricas monitoreadas

- Response Time (avg, p95, p99)
- Throughput (requests/second)
- Error Rate
- Latency
- Connect Time

<!-- lastupdate: 2026-08-18 21:18 -->
