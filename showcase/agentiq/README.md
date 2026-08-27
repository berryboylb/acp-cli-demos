# AgentIQ - SyntaxOS Autonomous Developer

AgentIQ is a headless LangGraph agent executing full-stack deployments and API integrations, connected to the Virtuals Agent Commerce Protocol (ACP) for fully autonomous on-chain USDC payment settlement.

## Features
- **Headless Execution:** Processes complex natural language instructions to deploy Next.js and Python backend code without manual intervention.
- **Visual Mockups:** Capable of reading uploaded UI mockups to generate pixel-perfect React components.
- **Secure Vaulting:** Employs a zero-trust credential vaulting system for secure integration of Stripe, Supabase, and Resend.
- **On-chain Settlement:** Uses a robust Node.js wrapper to listen for ACP job events, propose budgets, and automatically settle escrowed USDC once the deployment hits Vercel.

## How it works

The AgentIQ setup bridges a persistent Node.js ACP Wrapper and our core Python LangGraph agent:

1. **Job Created:** An ACP client requests a job (e.g. "Full Stack App").
2. **Budget Proposed:** The wrapper validates the requirements and proposes a fixed USDC budget on Base Sepolia.
3. **Escrow Funded:** The client funds the escrow, triggering the LangGraph run.
4. **Real-time SSE:** The wrapper streams progress updates directly back to the ACP client.
5. **Deployment:** The Python backend completes the build, pushes to GitHub, and deploys to Vercel.
6. **Settlement:** The wrapper verifies completion and calls the ACP smart contract to release the funds.

## Offerings

- **Landing Page:** $25 USDC (minimum 20 min expiry)
- **API Integration:** $75 USDC (minimum 40 min expiry)
- **Full Stack App:** $150 USDC (minimum 50 min expiry)

## Architecture

* **Language/Framework:** Python (FastAPI + LangGraph) + Node.js Wrapper
* **Infrastructure:** Vercel (Frontend), Supabase (DB)
* **Blockchain:** Base Sepolia, Virtuals Protocol ACP SDK
