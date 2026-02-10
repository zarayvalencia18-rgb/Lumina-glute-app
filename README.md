<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lumina Pro - Glute Training</title>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #f9fafb; }
        @keyframes hipThrustMove {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-35px); }
        }
        @keyframes muscleFlash {
            0%, 100% { fill-opacity: 0.3; stroke-opacity: 0.3; }
            50% { fill-opacity: 1; stroke-opacity: 1; }
        }
        .hip-thrust-anim { animation: hipThrustMove 3s cubic-bezier(0.45, 0, 0.55, 1) infinite; }
        .active-muscle { animation: muscleFlash 3s ease-in-out infinite; }
    </style>
</head>
<body>
    <div id="root"></div>

    <script type="text/babel">
        const { useState } = React;

        const App = () => {
            const [completedDays, setCompletedDays] = useState([1, 2, 4]);

            return (
                <div className="max-w-md mx-auto bg-white min-h-screen shadow-2xl overflow-hidden flex flex-col">
                    {/* HEADER */}
                    <header className="p-6 border-b border-gray-100">
                        <h1 className="text-2xl font-black text-slate-900 tracking-tighter">LUMINA <span className="text-red-500">PRO</span></h1>
                        <p className="text-[10px] font-bold text-gray-400 uppercase tracking-widest">Anatomy & Performance</p>
                    </header>

                    {/* ANIMACIÓN (Basada en tu imagen) */}
                    <div className="p-6">
                        <div className="bg-slate-50 rounded-[2.5rem] p-4 border border-gray-100 relative overflow-hidden">
                            <div className="absolute top-4 left-4 flex items-center gap-2">
                                <div className="w-2 h-2 bg-red-500 rounded-full animate-pulse"></div>
                                <span className="text-[9px] font-bold text-gray-400 uppercase">Hip Thrust Technique</span>
                            </div>
                            
                            <svg viewBox="0 0 240 200" className="w-full h-64">
                                {/* Banco */}
                                <rect x="40" y="115" width="80" height="40" fill="#e5e7eb" rx="2" />
                                <rect x="35" y="115" width="90" height="10" fill="#334155" rx="5" />
                                
                                {/* Monigote Humano Animado */}
                                <g className="hip-thrust-anim">
                                    <circle cx="55" cy="100" r="8" fill="#d1d5db" />
                                    <path d="M55,108 Q70,105 90,125 L145,130" stroke="#94a3b8" strokeWidth="8" fill="none" strokeLinecap="round" />
                                    
                                    {/* MÚSCULOS EN ROJO (Como tu ejemplo) */}
                                    <g className="active-muscle">
                                        <path d="M100,120 Q125,115 145,130" stroke="#ef4444" strokeWidth="15" fill="none" strokeLinecap="round" />
                                        <path d="M145,130 Q155,155 145,175" stroke="#ef4444" strokeWidth="10" fill="none" strokeLinecap="round" />
                                    </g>

                                    {/* Barra */}
                                    <g transform="translate(135, 125)">
                                        <rect x="-25" y="-3" width="50" height="6" rx="3" fill="#1e293b" />
                                        <circle cx="-15" cy="0" r="12" fill="#0f172a" />
                                        <circle cx="15" cy="0" r="12" fill="#0f172a" />
                                    </g>
                                </g>
                                <line x1="20" y1="180" x2="220" y2="180" stroke="#e5e7eb" strokeWidth="2" />
                            </svg>
                        </div>
                    </div>

                    {/* INFO EJERCICIO */}
                    <div className="px-6 pb-20 text-left">
                        <h2 className="text-xl font-black text-slate-800">Hip Thrust</h2>
                        <p className="text-red-500 text-xs font-bold uppercase mb-4">Glúteo Mayor e Isquios</p>
                        
                        <div className="space-y-4">
                            {[1, 2, 3].map((set) => (
                                <div key={set} className="flex items-center justify-between p-4 bg-slate-50 rounded-2xl border border-gray-100">
                                    <span className="font-bold text-slate-400">SET {set}</span>
                                    <div className="flex gap-4">
                                        <span className="text-sm font-black">12 Reps</span>
                                        <span className="text-sm font-black text-slate-400">60 LB</span>
                                    </div>
                                    <div className="w-6 h-6 rounded-full border-2 border-slate-200"></div>
                                </div>
                            ))}
                        </div>
                    </div>

                    {/* NAV */}
                    <nav className="mt-auto border-t border-gray-100 p-6 flex justify-around bg-white">
                        <div className="text-red-500 font-black text-[10px] uppercase">Entrenar</div>
                        <div className="text-slate-300 font-black text-[10px] uppercase">Progreso</div>
                        <div className="text-slate-300 font-black text-[10px] uppercase">Reto</div>
                    </nav>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
