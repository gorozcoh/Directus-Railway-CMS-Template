<div align="center">
  <img src="directus-logo-stacked.png" alt="Directus Logo" width="250" />
</div>

# Directus Railway CMS Template

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template)

A production-ready, one-click deployment template for [Directus](https://directus.io) on [Railway](https://railway.app).
Get a fully configured Directus backend with PostgreSQL database and Redis cache in minutes.

**Directus** lets you create, manage, and scale headless content. Design your data model, build powerful APIs, and
manage content for anything from simple websites to complex applications.

## What's Included

- **Directus** (v11.13.0) - Latest stable version with REST + GraphQL API
- **PostgreSQL Database** - Automatically provisioned and linked via Railway's private network (no egress fees)
- **Redis Cache** - Enabled by default for caching and WebSocket support
- **Railway S3 Storage** - Scalable file storage for multi-replica deployments
- **WebSockets** - Real-time features enabled by default
- **CMS Template** - Pre-configured content collections (pages, articles, etc.) applied automatically
- **Extensions Marketplace** - Access to extensions and plugins for enhanced functionality
- **Health Checks** - Built-in monitoring for Railway
- **Admin User** - Automatically created on first deployment
- **Frontend Starters** - Optional Next.js, Nuxt, Astro, and SvelteKit starters from
  [directus-labs/starters](https://github.com/directus-labs/starters)
- **Production Ready** - Configured with best practices for production use

## Use Cases

- **Content Management**: Enable teams to create, manage, and publish content without technical knowledge
- **API Development**: Build REST and GraphQL APIs from your database schema in minutes
- **Headless CMS**: Power websites, mobile apps, and other frontend applications with a flexible content API
- **Admin Panels**: Build custom admin interfaces for your applications
- **Data Management**: Visualize and manage data from any SQL database through an intuitive interface

## Quick Start

### Deploy to Railway

1. Click the [Deploy on Railway](https://railway.app/template) button above
2. Railway will automatically:
   - Generate a secure SECRET (encryption key)
   - Set your PUBLIC_URL (from your Railway domain)
   - Provision a PostgreSQL database
   - Provision a Redis cache
   - Provision Railway S3 storage
   - Link all services to Directus via private network
   - Deploy your Directus instance
   - Create your admin user (with default email, change after first login)
   - Generate a secure admin password (change after first login)
   - Apply CMS template with pre-configured collections
3. Once deployed, access your Directus admin panel at your Railway URL
4. **Optional**: Configure `ADMIN_EMAIL` and `ADMIN_PASSWORD` in Railway service variables if you want custom values
   (otherwise defaults are used)

### Frontend Templates

Deploy frontend starters alongside your Directus backend! See [FRONTEND_ADDONS.md](./FRONTEND_ADDONS.md) for complete
instructions.

**Available Frontend Starters:**

- **Next.js** - React framework with SSR/SSG support
- **Nuxt** - Vue.js framework with SSR/SSG support
- **Astro** - Content-focused framework with island architecture
- **SvelteKit** - Svelte framework with full-stack capabilities

**Quick Start:**

1. Deploy Directus CMS template (above)
2. Add optional frontend service from [directus-labs/starters](https://github.com/directus-labs/starters)
3. Configure environment variables to connect frontend to Directus
4. Deploy and start building!

See [FRONTEND_ADDONS.md](./FRONTEND_ADDONS.md) for detailed setup instructions and environment variable configuration
for each framework.

## Features

### Private Networking

All communication between services (Directus, PostgreSQL, Redis, Storage) happens over Railway's private network. This
means:

- **Zero egress fees** for database and cache operations
- **Secure** - services are not exposed externally by default
- **Fast** - private network communication is optimized

### Scalable Storage

Uses Railway's S3-compatible storage buckets instead of local volumes:

- **Multi-replica support** - share storage across multiple Directus instances
- **Persistent** - files survive container restarts
- **Scalable** - no storage limits tied to container size

### Automatic Setup

The CMS template includes automatic setup scripts that:

- Create admin user on first deployment
- Apply CMS template with pre-configured collections
- Configure S3 storage automatically
- Set up health checks

## Development

### Local Development

Run Directus locally using Docker Compose with the same configuration as Railway:

1. **Navigate to directus directory:**

   ```bash
   cd directus
   ```

2. **Set up environment variables:**

   ```bash
   cp .env.example .env
   # Edit .env with your values
   ```

3. **Start services:**

   ```bash
   docker-compose up -d
   ```

4. **Access Directus:**
   - Admin Panel: http://localhost:8055
   - Create admin account on first access (if ADMIN_EMAIL/PASSWORD not set)

See [LOCAL_SETUP.md](./LOCAL_SETUP.md) for complete local development guide, including:

- Environment variable configuration
- Differences between Railway and local setup
- Using S3 storage locally
- Troubleshooting tips

### Scripts

- `scripts/start-directus.sh` - Startup script that runs Directus bootstrap and optionally applies CMS template
- `scripts/bootstrap-admin.sh` - Admin user creation and template loading (CMS template only)

## Support

- **Directus Documentation**: https://docs.directus.io
- **Railway Documentation**: https://docs.railway.app
- **Directus Discord**: https://directus.chat

## License

MIT License - see [LICENSE](./LICENSE) file for details.
