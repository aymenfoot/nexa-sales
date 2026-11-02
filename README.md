# Nexa Sales

**Nexa Sales** is an AI-powered sales assistant widget for Shopify stores. It helps customers discover products, get personalized recommendations, and receive real-time answers, with an admin panel for customizing the widget and optional N8N integration for advanced AI processing.

Part of the **Nexa** portfolio.

## Highlights

- Smart product recommendations powered by AI.
- Real-time chat widget with customizable positioning and styling.
- Admin panel for colors, text, position, and behavior.
- Mobile-responsive, optimized for all device sizes.
- Optional N8N integration for advanced AI workflows.
- Real-time settings updates reflected immediately on the storefront.
- Built with Shopify security best practices.

## Architecture

- **Frontend:** Remix (TypeScript) + Shopify Polaris UI
- **Backend:** Node.js + Prisma ORM (SQLite in development)
- **Theme extension:** Liquid template with vanilla JavaScript
- **AI integration:** N8N webhooks with fallback processing
- **Authentication:** Shopify OAuth with session management

## Quick start

### Prerequisites

- Node.js 18+ and npm
- Shopify Partner account
- Shopify CLI 3.0+

### Installation

```bash
git clone https://github.com/aymenfoot/nexa-sales.git
cd nexa-sales
npm install
cp .env.example .env
# Edit .env with your Shopify app credentials (see SETUP.md)
cp shopify.app.example.toml shopify.app.toml
# Edit shopify.app.toml with your app details
npx prisma generate
npx prisma migrate dev
shopify app dev
```

### Configuration

Required values in `.env`:

- `SHOPIFY_API_KEY` — from Shopify Partner Dashboard (Client ID)
- `SHOPIFY_SALES_ASSISTANT_WIDGET_ID` — a UUID (generate at uuidgenerator.net)

Optional N8N integration:

- `N8N_WEBHOOK_URL` — your N8N webhook URL
- `N8N_API_KEY` — N8N API key (if authentication required)

See `SETUP.md` for detailed Shopify setup and `N8N_SETUP.md` for the N8N workflow.

### Testing

```bash
npx jest
```

20 tests covering the voice/chat widget behavior (jsdom environment).

### Build

```bash
npm run build
```

Produces the Remix production build (`build/`).

## Environment variables

See `.env.example` for the full list.

## License

MIT License. See [LICENSE](LICENSE).
