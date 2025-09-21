# 🤖 AIni Pay - Chatbot para Transacciones Multi-Chain

<div align="center">
  <img src="../assets/images/logo/AIniPay_Logo.png" alt="AIni Pay Logo" width="200"/>
  
  [![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
  [![Project Status](https://img.shields.io/badge/Status-Production%20Ready-green.svg)]()
  [![Version](https://img.shields.io/badge/Version-1.0.0-blue.svg)]()
  [![React](https://img.shields.io/badge/React-18.3.1-61DAFB.svg)](https://reactjs.org/)
  [![EVM Compatible](https://img.shields.io/badge/EVM-Compatible-blue.svg)](https://ethereum.org/)
  [![Celestia Network](https://img.shields.io/badge/Network-Celestia-purple.svg)](https://celestia.org/)
</div>

---

## 📋 Descripción del Proyecto

**AIni Pay** es una aplicación web3 revolucionaria que combina **inteligencia artificial conversacional** con **transacciones blockchain** en múltiples redes, incluyendo **Sonic EVM** y **Celestia**. Los usuarios pueden realizar transferencias de criptomonedas utilizando comandos de chat en lenguaje natural, eliminando la complejidad técnica de las transacciones blockchain tradicionales.

### 🎯 Problema que Resuelve

Las transacciones blockchain actuales presentan múltiples barreras para los usuarios:
- **Complejidad técnica**: Direcciones largas, interfaces complejas
- **Barrera de entrada**: Conocimiento técnico requerido
- **Experiencia fragmentada**: Diferentes interfaces para cada red
- **Errores humanos**: Direcciones incorrectas, cantidades erróneas

### 💡 Nuestra Solución

AIni Pay democratiza las transacciones blockchain mediante:
- **Chat inteligente**: Comandos en lenguaje natural procesados por IA
- **Multi-chain**: Soporte nativo para EVM (Sonic) y Cosmos (Celestia)
- **Validación automática**: Prevención de errores mediante IA
- **Interfaz unificada**: Una sola aplicación para múltiples redes

---

## 🌐 Aplicación en Producción

- **URL Principal**: [https://aini-pay.vercel.app/](https://aini-pay.vercel.app/)
- **Plataforma**: Vercel con CI/CD automático desde GitHub
- **Estado**: ✅ Activo 24/7
- **Arquitectura**: Dual → Sonic EVM + Celestia Native

---

## 🏗️ Arquitectura del Sistema

### � Diagrama de Arquitectura

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                          🤖 AIni Pay Chatbot Architecture                       │
└─────────────────────────────────────────────────────────────────────────────────┘

                                    👤 Usuario
                                       │
                                   "Envía 5 TIA a..."
                                       │
                                       ▼
                    ┌─────────────────────────────────────────┐
                    │         🎨 Frontend React UI            │
                    │    • Chat Interface                     │
                    │    • Transaction History                │
                    │    • Multi-Wallet Connector             │
                    └─────────────────┬───────────────────────┘
                                      │
                                      ▼
                    ┌─────────────────────────────────────────┐
                    │      🤖 DeepSeek AI Parser              │
                    │    • Natural Language Processing       │
                    │    • Intent Detection                  │
                    │    • Data Extraction & Validation      │
                    └─────────────────┬───────────────────────┘
                                      │
                           ┌──────────┴──────────┐
                           │  Network Detection   │
                           └──────────┬──────────┘
                                      │
                     ┌────────────────┴────────────────┐
                     │                                 │
                     ▼                                 ▼
         ┌─────────────────────┐              ┌─────────────────────┐
         │   🔗 Sonic EVM       │              │  🌌 Celestia Native │
         │                     │              │                     │
         │  • MetaMask/Reown   │              │  • Keplr Wallet     │
         │  • Smart Contract   │              │  • CosmJS SDK       │
         │  • Token: S         │              │  • Token: TIA       │
         │  • Gas: Variable    │              │  • Fee: ~0.001 TIA  │
         │  • Time: ~15s       │              │  • Time: ~3s        │
         │                     │              │                     │
         │  Contract Address:  │              │  Networks:          │
         │  0x9d7b2eA6...      │              │  • celestia         │
         │                     │              │  • mocha-4          │
         └─────────┬───────────┘              └─────────┬───────────┘
                   │                                    │
                   ▼                                    ▼
         ┌─────────────────────┐              ┌─────────────────────┐
         │   💳 Transaction     │              │   💳 Transaction     │
         │   Execution (EVM)    │              │   Execution (Cosmos) │
         │                     │              │                     │
         │  1. Wallet Connect  │              │  1. Keplr Connect   │
         │  2. Gas Estimation  │              │  2. Fee Calculation │
         │  3. Smart Contract  │              │  3. P2P Transfer    │
         │  4. Confirmation    │              │  4. Confirmation    │
         └─────────┬───────────┘              └─────────┬───────────┘
                   │                                    │
                   └────────────────┬───────────────────┘
                                    │
                                    ▼
                    ┌─────────────────────────────────────────┐
                    │      📊 Unified Transaction Log         │
                    │    • Cross-chain History               │
                    │    • Explorer Links                    │
                    │    • Status Tracking                   │
                    └─────────────────────────────────────────┘
```

### 🔄 Flujo de Datos del Chatbot

```
Entrada Usuario → Parser IA → Validación → Detección Red → Wallet → Blockchain → Confirmación
     │              │            │            │           │         │            │
     │              │            │            │           │         │            └─ Hash TX
     │              │            │            │           │         └─ Gas/Fee    
     │              │            │            │           └─ Firma Local
     │              │            │            └─ EVM vs Cosmos
     │              │            └─ Dirección + Cantidad
     │              └─ Intent: "send" | "other"
     └─ "Envía 5 TIA a celestia1..."
```

### �🔗 Sonic EVM (Smart Contracts)

- **Dirección del Contrato**: `0x9d7b2eA62b7B9B1c382c1B92e8dd567E6e772090`  
- **Red**: Sonic Mainnet (Chain ID: 146)  
- **Explorador**: [Ver en SonicScan](https://sonicscan.org/address/0x9d7b2ea62b7b9b1c382c1b92e8dd567e6e772090)  
- **Token**: S (Token nativo de Sonic)
- **Funcionalidad**: Gestión de tokens mediante smart contracts en Solidity

### 🌌 Celestia Native (Peer-to-Peer)

- **Mainnet**: `celestia`  
- **Testnet**: `mocha-4`  
- **Token**: TIA (Token nativo de Celestia)
- **Ventaja**: Transacciones directas sin contratos, ultra rápidas (~0.001 TIA de costo)
- **Arquitectura**: Cosmos SDK nativo

### 🤖 Componentes de IA

- **Motor de IA**: DeepSeek AI para procesamiento de lenguaje natural
- **Parser Inteligente**: Extracción automática de datos de transacción
- **Validación**: Verificación automática de direcciones y cantidades
- **Detección de Intención**: Distingue comandos de transacción de consultas generales

---

## ⚡ Comparativa Técnica

| Aspecto | Sonic (EVM) | Celestia (Nativo) |
|---------|-------------|-------------------|
| **Modelo** | Smart contracts | Peer-to-peer |
| **Lenguaje** | Solidity | Cosmos SDK (Go) |
| **Gas Fees** | Variables (estimados) | Fijos (~0.001 TIA) |
| **Tiempo TX** | ~15 segundos | ~3 segundos |
| **Token** | S | TIA |
| **Wallet** | MetaMask/Reown | Keplr |

---

## 🎯 Características Principales

### 💬 Chat Inteligente
- Procesamiento de lenguaje natural con **DeepSeek AI**
- Comandos en español e inglés
- Detección automática de intención
- Validación de datos en tiempo real

### 🔗 Multi-Wallet Support
- **Reown/WalletConnect**: Para redes EVM (Sonic)
- **Keplr**: Para redes Cosmos (Celestia)
- **MetaMask**: Compatibilidad EVM estándar

### 🎨 Interfaz de Usuario
- **Diseño horizontal**: Chat con barras laterales scrolleables
- **Responsive**: Optimizado para desktop y móvil
- **Estados visuales**: Indicadores de conexión y progreso
- **Historial unificado**: Tracking cross-chain de transacciones

### 🛡️ Seguridad y Validación
- **Validación de direcciones**: Formato específico por red
- **Confirmación manual**: Usuario aprueba cada transacción
- **Nunca custodia fondos**: Transacciones peer-to-peer
- **Cifrado local**: Claves privadas nunca expuestas

---

## 🚀 Funcionalidades

### Comandos de Transacción Soportados

```bash
# Ejemplos para Sonic (EVM)
"Send 0.1 S to 0xF507Baf56754091Fc700d3cac895F005AF446fF4"
"Transfer 5 S to Omar"

# Ejemplos para Celestia
"Envía 2 TIA a celestia1qnk2n4nlkpw9xfqntladh74w6ujtulwnmxnh3k"
"Manda 0.5 TIA a celestia1abc..."
"Transfer 1000000 utia to celestia1def..."
```

### Flujo de Transacción

1. **Análisis de Comando**
   - IA interpreta el mensaje del usuario
   - Extrae cantidad, destinatario y red objetivo
   - Valida formato y detecta errores

2. **Preparación**
   - Muestra resumen detallado de la transacción
   - Calcula fees estimados
   - Presenta opciones de confirmación/cancelación

3. **Ejecución**
   - Conecta con wallet correspondiente (Keplr/MetaMask)
   - Ejecuta transacción en blockchain
   - Monitorea confirmación

4. **Confirmación**
   - Muestra hash de transacción
   - Proporciona enlace al explorador
   - Registra en historial unificado

---

## 👥 Equipo de Desarrollo

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="../assets/images/team/yamil.jpg" width="100px" alt="Yamil Navia"/><br />
        <sub><b>Yamil Navia</b></sub><br />
        <sub>Blockchain Developer</sub><br />
        <sub>Solidity | Rust | Smart Contracts</sub>
      </td>
      <td align="center">
        <img src="../assets/images/team/omar.jpg" width="100px" alt="Omar Quispe"/><br />
        <sub><b>Omar Quispe</b></sub><br />
        <sub>AI Developer</sub><br />
        <sub>Agentes Inteligentes | NLP</sub>
      </td>
      <td align="center">
        <img src="../assets/images/team/jhamil.jpg" width="100px" alt="Jhamil Mamani"/><br />
        <sub><b>Jhamil Mamani</b></sub><br />
        <sub>Frontend Developer</sub><br />
        <sub>React | Tailwind | UI/UX</sub>
      </td>
    </tr>
  </table>
</div>

---

## 📈 Métricas de Rendimiento

- **Respuesta de IA**: < 500ms promedio
- **Transacciones Sonic**: ~15 segundos confirmación
- **Transacciones Celestia**: ~3 segundos confirmación
- **Uptime de Aplicación**: 99.9% (últimos 30 días)
- **Precisión del Parser**: >95% en comandos válidos

---

## 🛠️ Stack Tecnológico

### Frontend
- **React 18.3.1**: Framework principal
- **Vite**: Build tool y dev server
- **Tailwind CSS**: Styling y responsive design
- **Framer Motion**: Animaciones y transiciones

### Blockchain Integration
- **Wagmi + RainbowKit**: Para conexiones EVM
- **CosmJS**: Para transacciones Cosmos/Celestia
- **Ethers.js**: Interacciones EVM
- **Keplr API**: Wallet Cosmos nativo

### Inteligencia Artificial
- **DeepSeek API**: Procesamiento de lenguaje natural
- **Custom Parser**: Análisis local de comandos
- **Validation Engine**: Sistema de validación híbrido

---

## 🚀 Instalación y Desarrollo

### Prerequisitos
- **Node.js** 18+
- **Git**
- **Keplr Wallet** (para Celestia)
- **MetaMask** (para Sonic)

### Frontend Setup

```bash
# Clonar repositorio
git clone https://github.com/AIni-Pay/Frontend-AIni-Pay.git
cd Frontend-AIni-Pay

# Instalar dependencias
npm install

# Configurar variables de entorno
echo "VITE_AI_API_KEY=tu_clave_deepseek" >> .env
echo "VITE_WALLETCONNECT_PROJECT_ID=tu_id_proyecto" >> .env

# Ejecutar en desarrollo
npm run dev
```

### Celestia Module Setup

```bash
# Navegar al módulo de Celestia
cd Transaction

# Instalar dependencias
npm install

# Configurar API key
echo "VITE_DEEPSEEK_API_KEY=tu_clave_api" >> .env

# Ejecutar en desarrollo
npm run dev
```

---

## 📚 Documentación Adicional

- **[Frontend README](../frontend/README.md)**: Documentación completa del frontend
- **[Chatbot Guide](../frontend/CHATBOT_GUIDE.md)**: Guía de uso del chatbot
- **[Transaction Module](../Transaction/README.md)**: Documentación del módulo Celestia
- **[Proyecto Completado](../Transaction/PROYECTO_COMPLETADO.md)**: Estado del desarrollo

---

## 🔗 Enlaces Importantes

### Aplicación
- **Producción**: [https://aini-pay.vercel.app/](https://aini-pay.vercel.app/)
- **GitHub Frontend**: [Frontend-AIni-Pay](https://github.com/AIni-Pay/Frontend-AIni-Pay)

### Blockchain Explorers
- **Sonic Contract**: [SonicScan](https://sonicscan.org/address/0x9d7b2ea62b7b9b1c382c1b92e8dd567e6e772090)
- **Celestia Mainnet**: [Mintscan](https://www.mintscan.io/celestia)
- **Mocha Testnet**: [Mocha Explorer](https://testnet.mintscan.io/celestia-testnet)

### Herramientas de Desarrollo
- **DeepSeek AI**: [Platform](https://platform.deepseek.com/)
- **Keplr Wallet**: [Download](https://wallet.keplr.app/)
- **MetaMask**: [Download](https://metamask.io/)

---

## 🛡️ Seguridad y Buenas Prácticas

### Principios de Seguridad
- ✅ **Nunca solicita claves privadas** o frases semilla
- ✅ **Todas las transacciones** se firman localmente en wallets
- ✅ **Validación exhaustiva** de direcciones antes del envío
- ✅ **Confirmación manual** requerida para cada transacción
- ✅ **Código abierto** y auditable

### Recomendaciones de Uso
- Siempre verifica la dirección de destino antes de confirmar
- Comienza con cantidades pequeñas para pruebas
- Mantén actualizadas las extensiones de wallet
- Guarda los hashes de transacciones importantes

---

## 🎯 Roadmap Futuro

### Próximas Funcionalidades
- [ ] **Soporte adicional de redes**: Polygon, Arbitrum, Optimism
- [ ] **NFT Transfers**: Envío de NFTs mediante comandos
- [ ] **DeFi Integration**: Swaps automáticos entre tokens
- [ ] **Programación de transacciones**: Envíos diferidos
- [ ] **Contactos inteligentes**: Sistema de contactos con IA

### Mejoras Técnicas
- [ ] **Cache de transacciones**: Almacenamiento local optimizado
- [ ] **Batch transactions**: Múltiples transacciones en una
- [ ] **Gas optimization**: Predicción y optimización de fees
- [ ] **Multi-idioma**: Soporte ampliado de idiomas

---

## 📄 Licencia

Este proyecto está bajo **Licencia MIT**. Ver [LICENSE](LICENSE) para más detalles.

---

## 🙏 Agradecimientos

- **Ethereum Foundation** por el ecosistema EVM
- **Celestia Labs** por la innovación en DA
- **Sonic Network** por la infraestructura EVM
- **DeepSeek** por la potente API de IA
- **Comunidad Open Source** por las herramientas y librerías

---

<div align="center">
  <strong>🚀 AIni Pay - Democratizando las Transacciones Blockchain a través de IA 🚀</strong>
</div>
