'use client';

import { motion } from 'framer-motion';

export default function Hero() {
  const scrollToAbout = () => {
    const aboutSection = document.getElementById('about');
    if (aboutSection) {
      aboutSection.scrollIntoView({ behavior: 'smooth' });
    }
  };

  return (
    <section className="relative flex flex-col items-center justify-center min-h-screen px-6 bg-black text-white overflow-hidden">
      {/* GRADIENT BACKGROUND */}
      <div className="absolute inset-0 bg-gradient-to-br from-purple-500/30 via-pink-400/20 to-transparent pointer-events-none z-0" />

      <div className="text-center max-w-4xl z-10 mt-24">
        {/* HEADING */}
        <motion.h1
          initial={{ opacity: 0, y: -40 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.8 }}
          className="text-4xl md:text-6xl font-bold mb-6 leading-tight"
        >
          Revolutionizing Digital Commerce with <br />
          <span className="text-transparent bg-clip-text bg-gradient-to-r from-white via-purple-400 to-white">
            AI Blockchain
          </span>
        </motion.h1>

        {/* SUBTEXT */}
        <motion.p
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ delay: 0.4, duration: 0.6 }}
          className="text-white/70 mb-10 text-lg"
        >
          We’ve heard that exceeding our customers’ expectations is beyond reach.
          <br />
          Instead of reinventing the wheel, we’ve chosen to enhance it.
        </motion.p>

        {/* BUTTON */}
        <motion.button
          whileHover={{ scale: 1.05 }}
          onClick={scrollToAbout}
          className="relative inline-flex items-center px-7 py-3 rounded-full border border-white/30 text-white font-medium backdrop-blur-sm overflow-hidden"
        >
          <span className="relative z-10">✨ Get Started</span>

          {/* GLOW ANIMATION */}
          <motion.span
            className="absolute left-[-150%] top-0 w-full h-full bg-white/20 blur-2xl"
            animate={{ left: ['-150%', '150%'] }}
            transition={{
              repeat: Infinity,
              duration: 2.5,
              ease: 'linear',
            }}
          />
        </motion.button>
      </div>
    </section>
  );
}
