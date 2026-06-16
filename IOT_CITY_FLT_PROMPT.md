# 🌆 IoT City Flutter App — Prompt de Desarrollo

> **App:** `iot_city_flt`  
> **Plataforma:** Flutter / Android 16.0+  
> **Propósito:** Dashboard moderno de métricas urbanas con gráficos interactivos  
> **Basado en:** IoT City Platform (backend Python + API REST)

---

## 🎯 Objetivo

Crear una aplicación Flutter llamada **`iot_city_flt`** que funcione como dashboard moderno y profesional para la plataforma IoT City, mostrando métricas de negocio, energía y fitness en un solo flujo visualmente impactante.

---

## 📐 Stack Tecnológico

| Componente | Tecnología |
|------------|------------|
| Framework | Flutter 3.x+ (Dart) |
| Gráficos | fl_chart (líneas, barras, circular) |
| Estado | Provider / Riverpod |
| HTTP | dio / http |
| WebSocket | web_socket_channel |
| Animaciones | implicit_animations / manual |
| Mínima SDK | Android 16.0 (API 36) |
| Target | Android, iOS, Web |

---

## 🎨 Paletas de Colores (20 opciones)

Seleccionar una o crear una combinación personalizada:

| # | Nombre | Colores |
|---|--------|---------|
| 1 | **Sunset Orange** | Coral, Naranja intenso, Terracota, Beige cálido, Marrón suave, Amarillo dorado |
| 2 | **Teal Breeze** | Verde agua, Turquesa, Teal profundo, Gris claro, Blanco, Azul cielo |
| 3 | **Gray Steel** | Gris claro, Gris medio, Gris oscuro, Plata, Negro carbón, Blanco humo |
| 4 | **Brown Earth** | Beige arena, Marrón claro, Marrón medio, Chocolate, Terracota, Crema |
| 5 | **Ocean Blue** | Azul marino, Azul cielo, Celeste, Turquesa, Blanco espuma, Gris azulado |
| 6 | **Pink Blossom** | Rosa pastel, Rosa fuerte, Fucsia, Coral, Blanco, Magenta |
| 7 | **Purple Mist** | Lavanda, Violeta claro, Púrpura, Morado intenso, Gris lila, Blanco |
| 8 | **Black Flame** | Negro profundo, Gris oscuro, Gris medio, Azul humo, Grafito, Blanco roto |
| 9 | **Navy Mirage** | Azul marino, Azul petróleo, Gris azulado, Negro, Azul acero, Blanco |
| 10 | **Golden Leaf** | Amarillo brillante, Dorado, Mostaza, Ocre, Marrón claro, Beige |
| 11 | **Rust Autumn** | Naranja oxidado, Terracota, Marrón rojizo, Beige cálido, Rojo ladrillo, Crema |
| 12 | **Ice Sky** | Azul hielo, Celeste, Blanco, Gris claro, Azul profundo, Azul humo |
| 13 | **Rosewood** | Rojo vino, Burdeos, Marrón oscuro, Rosa viejo, Beige cálido, Negro |
| 14 | **Emerald Forest** | Verde esmeralda, Verde bosque, Verde oliva, Verde claro, Marrón tierra, Blanco |
| 15 | **Sand Dune** | Beige arena, Marrón claro, Marrón medio, Gris cálido, Crema, Blanco |
| 16 | **Lavender Dream** | Lila pastel, Lavanda, Violeta, Púrpura suave, Gris claro, Blanco |
| 17 | **Copper Glow** | Cobre, Bronce, Marrón rojizo, Dorado, Beige cálido, Negro |
| 18 | **Skyline Gray** | Gris claro, Gris medio, Gris oscuro, Azul humo, Negro, Blanco |
| 19 | **Berry Punch** | Fucsia, Magenta, Morado intenso, Violeta, Rosa fuerte, Blanco |
| 20 | **Mint Fresh** | Verde menta, Verde agua, Turquesa claro, Blanco, Gris suave, Celeste |

---

## 📋 Requisitos Funcionales

### 1. Estilo Visual
- [ ] Fondo oscuro o con gradiente suave (azules, púrpuras o tonos elegantes)
- [ ] Tipografía clara y minimalista
- [ ] Gráficos bien definidos: líneas, barras y gauges circulares
- [ ] Iconografía simple y moderna para navegación

### 2. Paneles Principales
- [ ] **Revenue**: Gráfico de líneas con valores destacados por día
- [ ] **Total Sales**: Gráfico de barras con total acumulado
- [ ] **Successful Transactions**: Indicador circular de porcentaje + valores absolutos
- [ ] **Returning Customer Rate**: Gauge circular con porcentaje y métricas
- [ ] **Sales Target Completed**: Gauge circular en alerta (rojo/naranja) con progreso

### 3. Interactividad
- [ ] Opciones de filtrado por día, semana, mes y semestre
- [ ] Animaciones suaves al actualizar datos
- [ ] Navegación intuitiva entre secciones (energía, fitness, ventas)

### 4. Datos Adicionales
- [ ] Métricas clave: duración, calorías, velocidad promedio, frecuencia cardíaca
- [ ] Sección de facturación estimada y comparación con períodos anteriores
- [ ] Actividades seleccionables (Yoga, Running, Cycling) con iconos

### 5. Configuración
- [ ] Paleta de colores seleccionable desde la app
- [ ] Personalización de dashboard
- [ ] Exportación de reportes

---

## 🏗️ Estructura del Proyecto (Propuesta)

```
iot_city_flt/
├── android/
├── ios/
├── lib/
│   ├── main.dart
│   ├── app.dart
│   ├── config/
│   │   ├── theme.dart
│   │   ├── palettes.dart
│   │   └── constants.dart
│   ├── models/
│   │   ├── metrics.dart
│   │   ├── revenue.dart
│   │   ├── sales.dart
│   │   └── activity.dart
│   ├── providers/
│   │   ├── metrics_provider.dart
│   │   ├── filter_provider.dart
│   │   └── theme_provider.dart
│   ├── services/
│   │   ├── api_service.dart
│   │   └── websocket_service.dart
│   ├── screens/
│   │   ├── dashboard_screen.dart
│   │   ├── analytics_screen.dart
│   │   ├── settings_screen.dart
│   │   └── activities_screen.dart
│   ├── widgets/
│   │   ├── charts/
│   │   │   ├── line_chart_widget.dart
│   │   │   ├── bar_chart_widget.dart
│   │   │   └── circular_gauge_widget.dart
│   │   ├── cards/
│   │   │   ├── metric_card.dart
│   │   │   ├── revenue_card.dart
│   │   │   └── activity_card.dart
│   │   ├── filters/
│   │   │   └── time_filter.dart
│   │   └── layout/
│   │       └── responsive_grid.dart
│   └── utils/
│       ├── formatters.dart
│       └── mock_data.dart
├── assets/
│   ├── icons/
│   └── fonts/
├── test/
├── pubspec.yaml
├── TODO.md
├── DEPLOY.md
├── ARCHITECTURE.md
├── API.md
├── README.md
├── CONTRIBUTING.md
└── .gitignore
```

---

## 🔌 Integración con Backend IoT City

### API Endpoints

```dart
// Base URL
const String baseUrl = 'http://<host>:5062/api';

// Métricas del dashboard
GET  /dashboard/summary          // Resumen global
GET  /dashboard/zones             // Métricas por zona
GET  /dashboard/timeseries/global // Serie temporal global
GET  /dashboard/timeseries/{id}   // Serie temporal por nodo
GET  /dashboard/node/{id}         // Detalle de nodo
GET  /dashboard/traffic           // Tráfico de red
WS   /dashboard/ws                // Tiempo real

// Dispositivos
GET  /devices                     // Listar dispositivos
POST /devices/{id}/toggle         // ON/OFF

// Administración
GET  /admin/settings              // Configuración
PUT  /admin/settings              // Actualizar configuración
POST /admin/reset                 // Resetear sistema
```

### Mock Data (Desarrollo Offline)

Para desarrollo sin backend, usar datos mock:

```dart
class MockMetricsData {
  static List<RevenuePoint> getRevenue() => [
    RevenuePoint(day: 'Lun', value: 2450),
    RevenuePoint(day: 'Mar', value: 3200),
    RevenuePoint(day: 'Mié', value: 2800),
    RevenuePoint(day: 'Jue', value: 4100),
    RevenuePoint(day: 'Vie', value: 3800),
    RevenuePoint(day: 'Sáb', value: 5100),
    RevenuePoint(day: 'Dom', value: 4300),
  ];

  static SalesMetrics getSales() => SalesMetrics(
    totalSales: 28450,
    target: 35000,
    successfulTransactions: 342,
    totalTransactions: 400,
    returningCustomerRate: 0.68,
  );
}
```

---

## 🎨 Diseño de UI/UX

### Principios de Diseño
- **Minimalista y profesional:** Menos es más
- **Contraste:** Fondo oscuro con acentos de color
- **Jerarquía visual:** KPIs principales destacados
- **Micro-interacciones:** Hover states, transiciones suaves
- **Responsive:** Adaptable a diferentes tamaños de pantalla

### Layout Propuesto

```
┌──────────────────────────────────────────────────┐
│  📊 IoT City Dashboard          [Filtros] [⚙️]   │
├──────────────────────────────────────────────────┤
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌────────┐ │
│  │ Revenue │ │ Sales   │ │ Trans.  │ │ Return │ │
│  │ $28.5K  │ │ 81%     │ │ 85.5%   │ │ 68%    │ │
│  └─────────┘ └─────────┘ └─────────┘ └────────┘ │
├──────────────────────────────────────────────────┤
│  ┌────────────────────┐ ┌────────────────────┐   │
│  │ 📈 Revenue Chart   │ │ 📊 Sales Chart     │   │
│  │ (Líneas por día)   │ │ (Barras acumuladas)│   │
│  └────────────────────┘ └────────────────────┘   │
├──────────────────────────────────────────────────┤
│  ┌────────────┐ ┌────────────┐ ┌──────────────┐ │
│  │ 🔵 Trans. │ │ 🟣 Return  │ │ 🔴 Target    │ │
│  │ (Gauge %)  │ │ (Gauge %)  │ │ (Gauge alerta)│ │
│  └────────────┘ └────────────┘ └──────────────┘ │
├──────────────────────────────────────────────────┤
│  🏃 Activities:  [🧘 Yoga] [🏃 Running] [🚴 Cycling]│
│  ┌──────────────────────────────────────────────┐│
│  │ Duración: 45min  Calorías: 320  BPM: 145    ││
│  └──────────────────────────────────────────────┘│
└──────────────────────────────────────────────────┘
```

---

## 📦 Dependencias Flutter (pubspec.yaml)

```yaml
dependencies:
  flutter:
    sdk: flutter
  # Gráficos
  fl_chart: ^0.70.0
  # Estado
  provider: ^6.1.0
  # Red
  http: ^1.2.0
  dio: ^5.4.0
  web_socket_channel: ^3.0.0
  # UI
  google_fonts: ^6.2.0
  lucide_icons: ^0.0.3
  shimmer: ^3.0.0
  # Utilidades
  intl: ^0.19.0
  json_annotation: ^4.9.0
  # Almacenamiento
  shared_preferences: ^2.3.0
```

---

## 📐 API de la App

### Endpoints Internos (Provider)

```dart
// Providers
class MetricsProvider extends ChangeNotifier {
  MetricsSummary? summary;
  List<RevenuePoint> revenue;
  bool isLoading;
  
  Future<void> fetchMetrics();
  void connectWebSocket();
  void dispose();
}

class FilterProvider extends ChangeNotifier {
  TimeFilter currentFilter; // day, week, month, semester
  void setFilter(TimeFilter filter);
}
```

---

## 🧪 Tests

- [ ] Unit tests para providers
- [ ] Widget tests para cards y gráficos
- [ ] Integration tests para flujo completo
- [ ] Test de rendimiento (gráficos con muchos datos)

---

## 📚 Archivos de Documentación Requeridos

| Archivo | Propósito |
|---------|-----------|
| `README.md` | Descripción general, instalación rápida |
| `ARCHITECTURE.md` | Arquitectura de la app Flutter |
| `API.md` | Documentación de la API de backend |
| `DEPLOY.md` | Guía de despliegue y building |
| `TODO.md` | Tareas pendientes y roadmap |
| `CONTRIBUTING.md` | Guía para contribuidores |
| `.gitignore` | Archivos ignorados por git |

---

## ✅ Criterios de Aceptación

- [ ] Dashboard funcional con datos mock sin backend
- [ ] Conexión WebSocket para tiempo real
- [ ] 5+ tipos de gráficos interactivos
- [ ] Filtros temporales funcionales
- [ ] Paleta de colores configurable
- [ ] Animaciones suaves en transiciones
- [ ] Código modular y documentado
- [ ] Tests unitarios para lógica core
- [ ] Build exitoso para Android 16.0
