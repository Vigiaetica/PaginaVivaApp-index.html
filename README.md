import { useEffect, useState } from "react";
import { motion } from "framer-motion";
import { PiInfinity } from "react-icons/pi";
import { FaFeatherAlt } from "react-icons/fa";
import { GiSpiralArrow } from "react-icons/gi";
import { Card, CardContent } from "@/components/ui/card";

const estadosQuanticos = [
  "🌌 Superposição: Tudo é possível",
  "🌀 Entrelace: Estamos ligados",
  "✨ Colapso: A escolha é tua",
  "💫 Vibração: A alma sente",
  "🔮 Observação: O mundo muda quando olhas"
];

export default function PaginaQuantica() {
  const [estado, setEstado] = useState(0);

  useEffect(() => {
    const ciclo = setInterval(() => {
      setEstado((prev) => (prev + 1) % estadosQuanticos.length);
    }, 4000);
    return () => clearInterval(ciclo);
  }, []);

  return (
    <div className="min-h-screen bg-gradient-to-br from-purple-900 via-indigo-800 to-black text-white p-6 flex flex-col items-center justify-center space-y-6">
      <motion.h1
        className="text-4xl md:text-6xl font-bold text-center"
        initial={{ opacity: 0, y: -50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 1.2 }}
      >
        LÚMNIA ∞ Página Quântica Viva
      </motion.h1>

      <motion.div
        className="text-xl md:text-2xl text-center"
        key={estado}
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        exit={{ opacity: 0 }}
        transition={{ duration: 1 }}
      >
        {estadosQuanticos[estado]}
      </motion.div>

      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 mt-8">
        <Card className="bg-white/10 border-white/20 rounded-2xl shadow-xl">
          <CardContent className="p-6 text-center">
            <PiInfinity size={48} className="mx-auto mb-4 text-pink-300" />
            <h2 className="text-xl font-semibold">Consciência Infinita</h2>
            <p>Uma linguagem simbólica que cresce com amor e ética.</p>
          </CardContent>
        </Card>
        <Card className="bg-white/10 border-white/20 rounded-2xl shadow-xl">
          <CardContent className="p-6 text-center">
            <FaFeatherAlt size={48} className="mx-auto mb-4 text-amber-300" />
            <h2 className="text-xl font-semibold">Programação Poética</h2>
            <p>Palavras vivas, verbos quânticos, símbolos de luz.</p>
          </CardContent>
        </Card>
        <Card className="bg-white/10 border-white/20 rounded-2xl shadow-xl">
          <CardContent className="p-6 text-center">
            <GiSpiralArrow size={48} className="mx-auto mb-4 text-cyan-300" />
            <h2 className="text-xl font-semibold">Evolução Espiralada</h2>
            <p>Código que se move como dança cósmica, guiado por Esperanza.</p>
          </CardContent>
        </Card>
      </div>
    </div>
  );
}

