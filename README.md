# Restow for Claude

Restow helps wholesale distributors see where stock is available and track orders. Ask Claude for the available units of a specific part by warehouse location, the fulfillment status of a sales order by customer PO reference, or the arrival status of a purchase order by supplier reference. With write access explicitly granted in Restow, Claude can also create or edit products and customers and add comments to existing records.

## Connect your workspace

Install the plugin in Claude and open its **Connectors** tab. Add or connect **Restow**, sign in to your Restow account, and approve one workspace where you are an administrator. Restow defaults to **Read-only**. Choose **Read and write** on the Restow consent screen if you want Claude to make changes you ask for. Manage or revoke your connection from **Connected Agents** in Restow.

In Claude Code, load the plugin and use `/mcp` to connect the Restow server. The skill appears as `/restow:restow-lookups`.

## Try a lookup

- Where is part RVW-100 available, and how many units are at each location?
- What is the Restow sales order number and status for customer PO RVW-SO-1001?
- Find the purchase order for supplier reference RVW-PO-2001. Has it arrived?

These prompts use sample references. Use references from your connected workspace.

## Data and permissions

The plugin provides a lookup skill and connects to the Restow API at `https://api.restow.io/api/v1/mcp`. Claude sends the tool name and arguments to Restow. Restow returns relevant results from the approved workspace, which may include inventory, product, customer, supplier, order, and sales information. With write approval, Restow also receives and saves the requested customer and product changes and comments. The bundle contains Markdown and JSON. Restow authenticates the connection through OAuth.

For questions about the plugin, contact [Core Platform Systems](https://coreplatforms.ai/#contact). See the [Restow privacy policy](https://restow.io/privacy/) and [terms of service](https://restow.io/terms/).

## License

The plugin software and documentation are available under the [MIT License](LICENSE). The Restow name and icon are Core Platform Systems Inc. branding.
