# odoo-mcp-pro (Portal Edition)

<p align="center">
  <a href="https://www.odoo.com"><img src="assets/odoo-logo.svg" alt="Odoo" height="60"/></a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://modelcontextprotocol.io"><img src="assets/mcp-logo.svg" alt="Model Context Protocol" height="60"/></a>
</p>

<h1 align="center">odoo-mcp-pro</h1>

<p align="center">
  AI connector for Odoo ERP -- talk to your business data using natural language.<br/>
  Search, create, update, and manage records -- just ask.
</p>

---

## About this fork

This project is a modified fork of the original **odoo-mcp-pro** project developed by Pantalytics.

The original project provides an MCP (Model Context Protocol) server that allows AI assistants such as Claude, ChatGPT, Cursor, Windsurf and other MCP-compatible tools to interact with Odoo ERP systems using natural language.

This fork extends that work with a custom MCP Portal layer and related integration functionality. The Portal itself is maintained separately in a private repository and is not included in this public codebase.

Because of these additional integrations and architectural changes:

* this repository should not be considered a drop-in replacement for the original upstream project
* self-contained operation is not guaranteed without the accompanying Portal components
* some functionality may fail or behave unexpectedly if the Portal layer is absent
* third-party forks based on this repository are likely to require substantial additional work to function correctly

If you are looking for a standalone MCP server for Odoo, the original upstream project from Pantalytics is likely the better starting point.

---

## What this project is

This project provides an MCP-compatible interface layer for Odoo ERP.

It allows AI assistants to securely interact with Odoo business data using natural language by exposing structured MCP tools over the Odoo API layer.

Examples include:

* searching records
* retrieving invoices, contacts, products, quotations and CRM opportunities
* creating or updating records
* importing data
* querying metadata and available models

The MCP layer is intended as an additional interface to Odoo, not as a replacement for the Odoo user interface.

Typical examples:

* "Show me all unpaid invoices over R50,000"
* "Find all open opportunities assigned to Andre"
* "Create a lead for Example Company"
* "Which sales orders have not yet been delivered?"

---

## What this project supports

* Odoo 14-19+
* JSON/2 API support for newer Odoo versions
* XML-RPC support for older Odoo versions
* MCP-compatible AI tools
* CRUD operations against Odoo models
* Natural-language interaction through AI assistants
* Single-tenant self-hosted deployments
* Portal-integrated deployments

Supported MCP operations include:

| Tool             | Function                                   |
| ---------------- | ------------------------------------------ |
| `search_records` | Search records with filters and pagination |
| `get_record`     | Retrieve specific records                  |
| `list_models`    | Enumerate available Odoo models            |
| `create_record`  | Create records                             |
| `update_record`  | Update records                             |
| `delete_record`  | Delete records                             |
| `import_records` | Bulk import and upsert operations          |
| `server_info`    | Server and connection information          |

---

## What this project does not provide

This repository does not provide:

* a standalone multi-tenant SaaS platform
* built-in public authentication for exposed HTTP mode
* a fully self-contained portal environment
* guaranteed compatibility with upstream releases
* production-grade security simply by exposing the MCP server directly to the internet

The HTTP transport mode should always be protected behind:

* a reverse proxy
* authentication
* firewall restrictions
* VPN access
* network segmentation

---

## Security model

Odoo remains the authoritative security layer.

All permissions continue to be enforced through:

* Odoo ACLs
* Odoo record rules
* Odoo user permissions
* Odoo API keys

This MCP layer does not bypass Odoo security controls.

The MCP server itself is intended to operate as a stateless connector layer.

---

## Licensing

This project remains based on software licensed under the Elastic License 2.0.

The original upstream project and associated licensing terms belong to Pantalytics and the original contributors.

In practical terms:

* you may use, modify and run the software internally
* you may adapt it for your own environments and business use
* you may not offer the software itself as a competing hosted SaaS service where prohibited by the Elastic License
* you must preserve existing license notices and attribution

Please review the original license text and upstream repository for the complete licensing terms.

---

## Attribution

This project is derived from:

* **odoo-mcp-pro** by Pantalytics
* originally forked from **mcp-server-odoo** by Andrey Ivanov

This repository contains additional modifications, integrations and architectural changes beyond the upstream implementation.
