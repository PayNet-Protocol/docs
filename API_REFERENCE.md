```markdown
# PayNet API Reference
## Facilitator API
### Verify Transaction
**Endpoint:** `POST /api/facilitator/verify`
**Request:**
```json
{
  "hash": "blockchain_transaction_hash",
  "amount": "1000000",
  "network": "solana",
  "token": "USDC"
}
Response (Success):

{
  "verified": true,
  "transaction": {
    "hash": "5x7Kj...",
    "amount": "1000000",
    "network": "solana",
    "status": "verified"
  }
}
Response (Failed):

{
  "verified": false,
  "error": "Transaction not found"
}
Networks
Network	Token	Min Confirmations
Solana	USDC	32
Base	USDC	12
Polygon	USDC	20
Avalanche	USDC	15
Rate Limits
FREE: 100k verifications/month, 5 req/s
BASIC: 500k verifications/month, 15 req/s ($1,200 worth of $PAYNET)
PRO: 1M verifications/month, 30 req/s ($2,500 worth of $PAYNET)
Example Integration
// Make payment to protected endpoint
const response = await fetch('/api/protected', {
  headers: {
    'X-Payment': JSON.stringify({
      hash: 'tx_hash_here',
      amount: '1000000',
      network: 'solana',
      token: 'USDC'
    })
  }
});
Visit paynet.network/quickstart for complete guide.

### **Step 5:** Click **"Commit new file"** button
### **Step 6:** Also update the README - click on README.md, click pencil icon, paste this:
```markdown
# PayNet Documentation
Complete documentation for PayNet protocol and tools.
## Contents
- [API Reference](API_REFERENCE.md) - Complete API documentation
- [Quick Start Guide](https://paynet.network/quickstart) - Get started in 2 minutes
- [Protocol Specification](https://github.com/PayNet-Protocol/x402-protocol) - x402 protocol details
## Links
- **Website**: https://paynet.network
- **Live Demo**: https://paynet.network/demo
- **Twitter**: https://x.com/PayNetProtocol
## Getting Help
Questions? Visit our [documentation page](https://paynet.network/documentation) or reach out on Twitter.
