<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simulador Hídrico 3D Avanzado - Santa Marta & Magdalena</title>
<!-- Tailwind CSS -->
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
<!-- Three.js Library -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<style>
body { background-color: #000000; color: #f8fafc; font-family: system-ui, -apple-system, sans-serif; overflow-x: hidden; }
/* Custom scrollbar for modern sleek look */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: #030712; }
::-webkit-scrollbar-thumb { background: #1e293b; border-radius: 4px; }
</style>
</head>
<body class="min-h-screen p-3 md:p-6 flex flex-col items-center">
​<!-- HEADER / TÍTULO -->
<header class="w-full max-w-5xl mb-4 text-center md:text-left flex flex-col md:flex-row md:items-center justify-between gap-3 bg-[#0a0f1d] p-4 rounded-2xl border border-slate-800 shadow-xl">
<div>
<p class="text-xs md:text-sm text-cyan-400 font-bold uppercase tracking-wider mb-1">Tratamiento y reúso de aguas residuales · Santa Marta & Magdalena</p>
<h1 class="text-xl md:text-2xl font-black text-white tracking-tight">Simulador Interactivo 3D del Sistema Hídrico</h1>
</div>
<div class="self-start md:self-auto bg-cyan-950/90 border border-cyan-700/60 text-cyan-300 text-xs px-3 py-1.5 rounded-full font-semibold tracking-wider shadow-inner">
MODELO 3D EN TIEMPO REAL
</div>
</header>
​<!-- CONTENEDOR PRINCIPAL -->
<main class="w-full max-w-5xl bg-[#050914] border border-slate-800/80 rounded-3xl p-4 md:p-6 shadow-2xl flex flex-col gap-5">
​<!-- VISTA ESPACIAL 3D -->
<section class="flex flex-col gap-3">
<div class="flex flex-col md:flex-row md:items-center justify-between">
<div>
<h2 class="text-base md:text-lg font-bold text-white flex items-center gap-2">
<span class="w-2.5 h-2.5 rounded-full bg-cyan-400 animate-pulse"></span>
Vista espacial del sistema hídrico
</h2>
<p class="text-xs text-slate-400">Alcantarilla a la izquierda · Planta de tratamiento con biofiltro central · Ciudad de Santa Marta a la derecha</p>
</div>
<div class="text-[11px] text-cyan-300/80 bg-cyan-950/50 px-2.5 py-1 rounded-lg border border-cyan-900 mt-2 md:mt-0">
Interactividad 3D Activa
</div>
</div>
​<!-- CANVAS CONTAINER -->
<div id="canvas-container" class="relative w-full h-[360px] md:h-[460px] rounded-2xl overflow-hidden border border-slate-800 bg-[#000000] cursor-grab active:cursor-grabbing shadow-inner">
<!-- Overlay de ayuda flotante -->
<div class="absolute bottom-3 left-1/2 transform -translate-x-1/2 bg-slate-900/90 backdrop-blur-md border border-slate-700/70 text-slate-200 text-xs px-4 py-2 rounded-xl pointer-events-none z-10 text-center shadow-lg flex items-center gap-2">
<svg class="w-4 h-4 text-cyan-400 animate-spin" fill="none" viewBox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle><path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path></svg>
<span>Arrastra para rotar · rueda o pellizca para acercar/alejar</span>
</div>
</div>
​<!-- LEYENDA DE COLORES -->
<div class="grid grid-cols-1 sm:grid-cols-3 gap-3 text-xs text-slate-300 bg-[#030712] p-3.5 rounded-2xl border border-slate-900">
<div class="flex items-center gap-2.5 bg-[#0a0f1d] p-2.5 rounded-xl border border-slate-800">
<span class="w-3.5 h-3.5 rounded-full bg-amber-500 shadow-md shadow-amber-500/50 inline-block border border-amber-300"></span>
<div>
<p class="font-bold text-amber-400">Agua Residual / Servida</p>
<p class="text-[10px] text-slate-400">Captación y Retorno desde Ciudad</p>
</div>
</div>
<div class="flex items-center gap-2.5 bg-[#0a0f1d] p-2.5 rounded-xl border border-slate-800">
<span class="w-3.5 h-3.5 rounded-full bg-cyan-400 shadow-md shadow-cyan-400/50 inline-block border border-cyan-200"></span>
<div>
<p class="font-bold text-cyan-300">Biofiltro Magnificado</p>
<p class="text-[10px] text-slate-400">Procesamiento visible mejorado</p>
</div>
</div>
<div class="flex items-center gap-2.5 bg-[#0a0f1d] p-2.5 rounded-xl border border-slate-800">
<span class="w-3.5 h-3.5 rounded-full bg-emerald-400 shadow-md shadow-emerald-400/50 inline-block border border-emerald-200"></span>
<div>
<p class="font-bold text-emerald-400">Distribución a Santa Marta</p>
<p class="text-[10px] text-slate-400">Suministro de agua tratada</p>
</div>
</div>
</div>
</section>
​<div class="w-full h-px bg-gradient-to-r from-transparent via-slate-800 to-transparent"></div>
​<!-- PARÁMETROS DE OPERACIÓN (CONTROLES) -->
<section class="flex flex-col gap-4">
<div class="flex justify-between items-center">
<h3 class="text-base font-bold text-white flex items-center gap-2">
<svg class="w-5 h-5 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6V4m0 2a2 2 0 100 4m0-4a2 2 0 110 4m-6 8a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4m6 6v10m6-2a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4"></path></svg>
Parámetros de operación
</h3>
<span class="text-xs text-cyan-400 bg-cyan-950/80 px-2.5 py-1 rounded-full border border-cyan-800 font-semibold">Variables Editables</span>
</div>
​<div class="grid grid-cols-1 md:grid-cols-3 gap-4">
<!-- Control 1: Caudal -->
<div class="bg-[#0a0f1d] p-4 rounded-2xl border border-slate-800 flex flex-col gap-3 shadow-md">
<div class="flex justify-between text-sm">
<span class="text-slate-300 font-medium">Caudal de entrada</span>
<span id="val-caudal" class="font-bold text-cyan-400">160 L/s</span>
</div>
<input type="range" id="range-caudal" min="50" max="300" value="160" class="w-full accent-cyan-400 cursor-pointer h-2 bg-slate-800 rounded-lg">
</div>
​<!-- Control 2: Diámetro de Tubería -->
<div class="bg-[#0a0f1d] p-4 rounded-2xl border border-slate-800 flex flex-col gap-3 shadow-md">
<div class="flex justify-between text-sm">
<span class="text-slate-300 font-medium">Diámetro de tubería</span>
<span id="val-diametro" class="font-bold text-cyan-400">0.8 m</span>
</div>
<input type="range" id="range-diametro" min="0.2" max="1.5" step="0.1" value="0.8" class="w-full accent-cyan-400 cursor-pointer h-2 bg-slate-800 rounded-lg">
</div>
​<!-- Control 3: Nivel de Embalse -->
<div class="bg-[#0a0f1d] p-4 rounded-2xl border border-slate-800 flex flex-col gap-3 shadow-md">
<div class="flex justify-between text-sm">
<span class="text-slate-300 font-medium">Nivel de embalse</span>
<span id="val-embalse" class="font-bold text-cyan-400">75%</span>
</div>
<input type="range" id="range-embalse" min="10" max="100" value="75" class="w-full accent-cyan-400 cursor-pointer h-2 bg-slate-800 rounded-lg">
</div>
</div>
​<!-- MÉTRICAS DE CÁLCULO EN TIEMPO REAL -->
<div class="grid grid-cols-2 md:grid-cols-4 gap-3 bg-[#030712] p-4 rounded-2xl border border-slate-900 text-center">
<div class="bg-[#0a0f1d] p-3 rounded-xl border border-slate-800">
<p class="text-[11px] text-slate-400 uppercase tracking-wide">Velocidad del agua</p>
<p id="calc-velocidad" class="text-base font-black text-emerald-400 mt-1">1.25 m/s</p>
</div>
<div class="bg-[#0a0f1d] p-3 rounded-xl border border-slate-800">
<p class="text-[11px] text-slate-400 uppercase tracking-wide">Eficiencia de planta</p>
<p id="calc-eficiencia" class="text-base font-black text-cyan-400 mt-1">94.2%</p>
</div>
<div class="bg-[#0a0f1d] p-3 rounded-xl border border-slate-800">
<p class="text-[11px] text-slate-400 uppercase tracking-wide">Presión de red</p>
<p id="calc-presion" class="text-base font-black text-amber-400 mt-1">2.4 bar</p>
</div>
<div class="bg-[#0a0f1d] p-3 rounded-xl border border-slate-800">
<p class="text-[11px] text-slate-400 uppercase tracking-wide">Reúso efectivo</p>
<p id="calc-reuso" class="text-base font-black text-emerald-400 mt-1">150.8 L/s</p>
</div>
</div>
</section>
​</main>
​<!-- SCRIPT DE THREE.JS Y SIMULACIÓN 3D -->
<script>
// --- 1. CONFIGURACIÓN DEL ENTORNO 3D ---
const container = document.getElementById('canvas-container');
const scene = new THREE.Scene();
scene.background = new THREE.Color(0x000000);
scene.fog = new THREE.FogExp2(0x000000, 0.028);
​const camera = new THREE.PerspectiveCamera(42, container.clientWidth / container.clientHeight, 0.1, 1000);
camera.position.set(0, 9.5, 13.5);
camera.lookAt(0, 0, 0);
​const renderer = new THREE.WebGLRenderer({ antialias: true });
renderer.setSize(container.clientWidth, container.clientHeight);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
container.appendChild(renderer.domElement);
​// Iluminación de estudio optimizada para fondo negro puro
const ambientLight = new THREE.AmbientLight(0xffffff, 1.2);
scene.add(ambientLight);
​const dirLight = new THREE.DirectionalLight(0x38bdf8, 2.0);
dirLight.position.set(8, 15, 10);
scene.add(dirLight);
​const pointLight = new THREE.PointLight(0x06b6d4, 4, 25);
pointLight.position.set(0, 5, 0);
scene.add(pointLight);
​// Grupo principal del mundo 3D
const worldGroup = new THREE.Group();
scene.add(worldGroup);
​// Suelo cibernético / Grid en neón
const gridHelper = new THREE.GridHelper(24, 24, 0x0284c7, 0x1e293b);
gridHelper.position.y = -0.3;
worldGroup.add(gridHelper);
​const baseGeo = new THREE.BoxGeometry(16, 0.4, 9);
const baseMat = new THREE.MeshStandardMaterial({ color: 0x030712, roughness: 0.8, metalness: 0.2 });
const baseMesh = new THREE.Mesh(baseGeo, baseMat);
baseMesh.position.set(0, -0.3, 0);
worldGroup.add(baseMesh);
​// --- 2. ESTACIÓN DE ALCANTARILLA / CAPTACIÓN (IZQUIERDA) ---
const sewerGroup = new THREE.Group();
sewerGroup.position.set(-8.5, 0, 1.2); // Alejado a la izquierda
​const sewerPit = new THREE.Mesh(
new THREE.CylinderGeometry(1.2, 1.0, 1.0, 24),
new THREE.MeshStandardMaterial({ color: 0x1e293b, metalness: 0.6, roughness: 0.3 })
);
sewerPit.position.y = 0.5;
sewerGroup.add(sewerPit);
​const manholeCover = new THREE.Mesh(
new THREE.CylinderGeometry(1.25, 1.25, 0.15, 24),
new THREE.MeshStandardMaterial({ color: 0xd97706, metalness: 0.8, roughness: 0.2 })
);
manholeCover.position.y = 1.05;
sewerGroup.add(manholeCover);
​// Agua residual visible en la alcantarilla
const sewerWater = new THREE.Mesh(
new THREE.CylinderGeometry(0.95, 0.95, 0.6, 24),
new THREE.MeshStandardMaterial({ color: 0xb45309, roughness: 0.2, emissive: 0x92400e, emissiveIntensity: 0.8 })
);
sewerWater.position.y = 0.5;
sewerGroup.add(sewerWater);
worldGroup.add(sewerGroup);
​// --- 3. PLANTA DE TRATAMIENTO CON BIOFILTRO MAGNIFICADO (CENTRO) ---
const plantGroup = new THREE.Group();
plantGroup.position.set(0, 0, 0); // Mantenida en el centro
​// Estructura de rejas / preliminar
const rejasMesh = new THREE.Mesh(
new THREE.BoxGeometry(1.2, 0.7, 1.6),
new THREE.MeshStandardMaterial({ color: 0x1e293b, metalness: 0.5 })
);
rejasMesh.position.set(-2.2, 0.35, 0);
plantGroup.add(rejasMesh);
​// Biofiltro principal magnificado (cilindro central grande)
const biofiltroGroup = new THREE.Group();
biofiltroGroup.position.set(0.5, 0, 0);
​const bioFilterWall = new THREE.Mesh(
new THREE.CylinderGeometry(2.4, 2.4, 2.6, 32, 1, true),
new THREE.MeshPhysicalMaterial({
color: 0x38bdf8,
roughness: 0.05,
metalness: 0.1,
transparent: true,
opacity: 0.5,
side: THREE.DoubleSide,
transmission: 0.9
})
);
bioFilterWall.position.y = 1.3;
biofiltroGroup.add(bioFilterWall);
​// Anillo superior decorativo
const bioRing = new THREE.Mesh(
new THREE.TorusGeometry(2.4, 0.1, 16, 32),
new THREE.MeshStandardMaterial({ color: 0x06b6d4, metalness: 0.9 })
);
bioRing.rotation.x = Math.PI / 2;
bioRing.position.y = 0.05;
biofiltroGroup.add(bioRing);
​// Agua del biofiltro (Nivel variable dinámico según embalse)
const biofiltroWater = new THREE.Mesh(
new THREE.CylinderGeometry(2.32, 2.32, 1.4, 32),
new THREE.MeshPhysicalMaterial({
color: 0x0ea5e9,
roughness: 0.05,
metalness: 0.2,
emissive: 0x0284c7,
emissiveIntensity: 1.2,
transparent: true,
opacity: 0.88
})
);
biofiltroWater.position.y = 0.8;
biofiltroGroup.add(biofiltroWater);
​// Superficie del agua con brillo
const bioWaterSurface = new THREE.Mesh(
new THREE.CircleGeometry(2.3, 32),
new THREE.MeshStandardMaterial({
color: 0x38bdf8,
emissive: 0x0ea5e9,
emissiveIntensity: 0.8,
roughness: 0.05,
metalness: 0.8,
transparent: true,
opacity: 0.95
})
);
bioWaterSurface.rotation.x = -Math.PI / 2;
bioWaterSurface.position.y = 1.5;
biofiltroGroup.add(bioWaterSurface);
​// Brazo distribuidor rotativo con aspersores grandes y visibles
const armGroup = new THREE.Group();
armGroup.position.set(0, 2.4, 0);
​const centerPole = new THREE.Mesh(
new THREE.CylinderGeometry(0.1, 0.1, 0.5, 16),
new THREE.MeshStandardMaterial({ color: 0xffffff, metalness: 0.9 })
);
armGroup.add(centerPole);
​const rotatingArm = new THREE.Mesh(
new THREE.BoxGeometry(4.4, 0.1, 0.15),
new THREE.MeshStandardMaterial({ color: 0x38bdf8, metalness: 0.9, roughness: 0.1 })
);
rotatingArm.position.y = 0.2;
armGroup.add(rotatingArm);
​// Gotas de aspersión grandes y brillantes
const sprayParticles = [];
for (let i = 0; i < 36; i++) {
const drop = new THREE.Mesh(
new THREE.SphereGeometry(0.06, 12, 12),
new THREE.MeshBasicMaterial({ color: 0x7dd3fc })
);
drop.position.set((Math.random() - 0.5) * 4.0, 0.15, (Math.random() - 0.5) * 4.0);
armGroup.add(drop);
sprayParticles.push(drop);
}
biofiltroGroup.add(armGroup);
plantGroup.add(biofiltroGroup);
worldGroup.add(plantGroup);
​// --- 4. CIUDAD DE SANTA MARTA ELEGANTE (DERECHA) ---
const cityGroup = new THREE.Group();
cityGroup.position.set(8.5, 0, 0); // Alejado a la derecha
​// Base de la ciudad
const cityBase = new THREE.Mesh(
new THREE.BoxGeometry(4.2, 0.2, 5.0),
new THREE.MeshStandardMaterial({ color: 0x0f172a, roughness: 0.7 })
);
cityGroup.add(cityBase);
​// Edificios modernos y elegantes (Tonos dorados, blancos y acero oscuro)
const buildingColors = [0x94a3b8, 0x38bdf8, 0xfbbf24, 0xe2e8f0, 0x64748b];
for (let x = 0; x < 3; x++) {
for (let z = 0; z < 3; z++) {
const h = 1.2 + Math.random() * 2.2;
const bGeo = new THREE.BoxGeometry(0.9, h, 0.9);
const matColor = buildingColors[(x + z) % buildingColors.length];
const bMat = new THREE.MeshStandardMaterial({
color: matColor,
roughness: 0.2,
metalness: 0.8,
emissive: matColor === 0xfbbf24 ? 0xd97706 : 0x000000,
emissiveIntensity: 0.2
});
const building = new THREE.Mesh(bGeo, bMat);
building.position.set(-1.2 + x * 1.2, h / 2, -1.2 + z * 1.2);
cityGroup.add(building);
}
}
worldGroup.add(cityGroup);
​// --- 5. TUBERÍAS Y FLUJO DE AGUA EN CIRCUITO CERRADO ---
const pipeMeshes = [];
const waterParticles = [];
​function createPipeNetwork(pathPoints, pipeColorHex, particleColorHex, particleCount = 30) {
for (let i = 0; i < pathPoints.length - 1; i++) {
const p1 = pathPoints[i];
const p2 = pathPoints[i + 1];
​const dx = p2.x - p1.x;
const dy = p2.y - p1.y;
const dz = p2.z - p1.z;
const distance = Math.sqrt(dx * dx + dy * dy + dz * dz);
​const pipeGeo = new THREE.CylinderGeometry(0.15, 0.15, distance, 16);
const pipeMat = new THREE.MeshStandardMaterial({
color: pipeColorHex,
roughness: 0.2,
metalness: 0.8,
transparent: true,
opacity: 0.9
});
const pipe = new THREE.Mesh(pipeGeo, pipeMat);
​pipe.position.set((p1.x + p2.x) / 2, (p1.y + p2.y) / 2, (p1.z + p2.z) / 2);
pipe.quaternion.setFromUnitVectors(
new THREE.Vector3(0, 1, 0),
new THREE.Vector3(dx, dy, dz).normalize()
);
​worldGroup.add(pipe);
pipeMeshes.push(pipe);
}
​for (let i = 0; i < particleCount; i++) {
const pGeo = new THREE.SphereGeometry(0.08, 16, 16);
const pMat = new THREE.MeshPhysicalMaterial({
color: particleColorHex,
emissive: particleColorHex,
emissiveIntensity: 1.2,
roughness: 0.1,
transmission: 0.5
});
const particle = new THREE.Mesh(pGeo, pMat);
​particle.userData = {
path: pathPoints,
progress: i / particleCount,
baseSpeed: 0.002,
speed: 0.002
};
worldGroup.add(particle);
waterParticles.push(particle);
}
}
​// Tubería 1: Alcantarilla (-8.5) -> Planta de Tratamiento (0) (Agua Residual - Ámbar)
const path1 = [
new THREE.Vector3(-8.5, 0.5, 1.2),
new THREE.Vector3(-4.5, 0.5, 1.2),
new THREE.Vector3(-4.5, 0.5, 0.0),
new THREE.Vector3(-2.4, 0.5, 0.0)
];
createPipeNetwork(path1, 0xd97706, 0xfbbf24, 28);
​// Tubería 2: Planta de Tratamiento (0) -> Ciudad Santa Marta (8.5) (Agua Tratada Limpia - Azul Brillante)
const path2 = [
new THREE.Vector3(2.4, 0.5, 0.0),
new THREE.Vector3(4.5, 0.5, 0.0),
new THREE.Vector3(4.5, 0.5, 1.8),
new THREE.Vector3(8.5, 0.5, 1.8),
new THREE.Vector3(8.5, 0.5, 0.8)
];
createPipeNetwork(path2, 0x0284c7, 0x38bdf8, 32);
​// Tubería 3: Retorno de Agua Sucia desde la Ciudad (8.5) -> Alcantarilla (-8.5) (Circuito Cerrado Largo)
const path3 = [
new THREE.Vector3(8.5, 0.3, -1.5),
new THREE.Vector3(8.5, 0.3, -3.8),
new THREE.Vector3(0.0, 0.3, -3.8),
new THREE.Vector3(-8.5, 0.3, -3.8),
new THREE.Vector3(-8.5, 0.3, 1.2)
];
createPipeNetwork(path3, 0x78350f, 0xd97706, 38);
​// --- 6. INTERACTIVIDAD CON MOUSE Y TOUCH ---
let isDragging = false;
let previousMousePosition = { x: 0, y: 0 };
​container.addEventListener('mousedown', (e) => { isDragging = true; previousMousePosition = { x: e.clientX, y: e.clientY }; });
container.addEventListener('mousemove', (e) => {
if (!isDragging) return;
const deltaX = e.clientX - previousMousePosition.x;
const deltaY = e.clientY - previousMousePosition.y;
worldGroup.rotation.y += deltaX * 0.005;
worldGroup.rotation.x += deltaY * 0.005;
worldGroup.rotation.x = Math.max(-0.25, Math.min(0.5, worldGroup.rotation.x));
previousMousePosition = { x: e.clientX, y: e.clientY };
});
window.addEventListener('mouseup', () => { isDragging = false; });
​container.addEventListener('touchstart', (e) => { isDragging = true; previousMousePosition = { x: e.touches[0].clientX, y: e.touches[0].clientY }; });
container.addEventListener('touchmove', (e) => {
if (!isDragging) return;
const deltaX = e.touches[0].clientX - previousMousePosition.x;
worldGroup.rotation.y += deltaX * 0.005;
previousMousePosition = { x: e.touches[0].clientX, y: e.touches[0].clientY };
});
window.addEventListener('touchend', () => { isDragging = false; });
​// --- 7. CONTROLES Y CÁLCULOS EN TIEMPO REAL ---
const rangeCaudal = document.getElementById('range-caudal');
const rangeDiametro = document.getElementById('range-diametro');
const rangeEmbalse = document.getElementById('range-embalse');
​const valCaudal = document.getElementById('val-caudal');
const valDiametro = document.getElementById('val-diametro');
const valEmbalse = document.getElementById('val-embalse');
​const calcVelocidad = document.getElementById('calc-velocidad');
const calcEficiencia = document.getElementById('calc-eficiencia');
const calcPresion = document.getElementById('calc-presion');
const calcReuso = document.getElementById('calc-reuso');
​function updateSimulationParameters() {
const Q = parseFloat(rangeCaudal.value);
const D = parseFloat(rangeDiametro.value);
const E = parseFloat(rangeEmbalse.value);
​valCaudal.innerText = Q + " L/s";
valDiametro.innerText = D.toFixed(1) + " m";
valEmbalse.innerText = E + "%";
​// Fórmulas hidráulicas en tiempo real
const area = Math.PI * Math.pow(D / 2, 2);
const velocity = (Q / 1000) / (area > 0 ? area : 0.1);
const efficiency = Math.min(99.8, 82 + (E * 0.12) - (Q * 0.008));
const pressure = (E * 0.028) + (D * 0.45);
const reuse = Q * (efficiency / 100);
​calcVelocidad.innerText = velocity.toFixed(2) + " m/s";
calcEficiencia.innerText = efficiency.toFixed(1) + "%";
calcPresion.innerText = pressure.toFixed(1) + " bar";
calcReuso.innerText = reuse.toFixed(1) + " L/s";
​// Actualizar escala visual del agua del biofiltro según nivel de embalse
const scaleY = Math.max(0.2, E / 70);
biofiltroWater.scale.set(1, scaleY, 1);
bioWaterSurface.position.y = 0.2 + (scaleY * 1.2);
​// Actualizar el grosor (escala X y Z) de las tuberías 3D en tiempo real según el diámetro seleccionado
const pipeThicknessScale = Math.max(0.4, D * 1.25);
pipeMeshes.forEach(pipe => {
pipe.scale.set(pipeThicknessScale, 1, pipeThicknessScale);
});
​// Actualizar velocidad de las partículas en las tuberías según caudal y diámetro
waterParticles.forEach(p => {
p.userData.speed = p.userData.baseSpeed * (Q / 100) * (0.8 / D);
});
}
​rangeCaudal.addEventListener('input', updateSimulationParameters);
rangeDiametro.addEventListener('input', updateSimulationParameters);
rangeEmbalse.addEventListener('input', updateSimulationParameters);
​// --- 8. LOOP DE ANIMACIÓN ---
const clock = new THREE.Clock();
​function animate() {
requestAnimationFrame(animate);
const elapsedTime = clock.getElapsedTime();
const Q = parseFloat(rangeCaudal.value);
​// Rotación automática suave si el usuario no interactúa
if (!isDragging) {
worldGroup.rotation.y += 0.0012;
}
​// Rotación del brazo aspersor del biofiltro (su velocidad depende del caudal)
armGroup.rotation.y = elapsedTime * (0.6 + (Q / 100));
​// Animación de las gotas cayendo del brazo del biofiltro
sprayParticles.forEach((drop) => {
drop.position.y -= 0.025 * (Q / 120);
if (drop.position.y < -0.1) {
drop.position.y = 0.2;
}
});
​// Animación del flujo de partículas a lo largo de los nodos de tuberías
waterParticles.forEach(p => {
p.userData.progress += p.userData.speed;
if (p.userData.progress >= 1) p.userData.progress = 0;
​const path = p.userData.path;
const totalSegments = path.length - 1;
const scaledProgress = p.userData.progress * totalSegments;
const segmentIndex = Math.floor(scaledProgress);
const segmentProgress = scaledProgress - segmentIndex;
​if (segmentIndex < totalSegments) {
const p1 = path[segmentIndex];
const p2 = path[segmentIndex + 1];
p.position.lerpVectors(p1, p2, segmentProgress);
}
});
​renderer.render(scene, camera);
}
animate();
​// Responsive resize
window.addEventListener('resize', () => {
camera.aspect = container.clientWidth / container.clientHeight;
camera.updateProjectionMatrix();
renderer.setSize(container.clientWidth, container.clientHeight);
});
</script>
</body>
</html>
