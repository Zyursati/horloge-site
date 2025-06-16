body {
  background-color: #0e0e0e;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  margin: 0;
  overflow: hidden;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  cursor: none;
}

/* HORLOGE avec LUEUR FORTEMENT PULSANTE */
.clock-container {
  position: relative;
  z-index: 1;
  border: 2px solid #ffffff88;
  background-color: #000000;
  color: white;
  padding: 40px 60px;
  border-radius: 16px;
  font-size: 4em;
  font-weight: bold;
  text-align: center;
  box-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
  animation: pulseGlow 3s infinite ease-in-out;
}

@keyframes pulseGlow {
  0%, 100% {
    box-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
  }
  50% {
    box-shadow: 0 0 60px rgba(255, 255, 255, 0.6);
  }
}

/* PARTICULES */
.particles-container {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0; left: 0;
  overflow: hidden;
  z-index: 0;
  pointer-events: none;
}

.particle {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background-color: #ffffff;
  opacity: 0;
  animation: blink 1.5s infinite;
  box-shadow: 0 0 8px rgba(255, 255, 255, 0.8);
}

@keyframes blink {
  0% { opacity: 0; }
  30% { opacity: 1; }
  70% { opacity: 0; }
  100% { opacity: 0; }
}
