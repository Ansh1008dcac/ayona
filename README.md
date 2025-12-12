# Ayona - API Request Collection

## Overview
This repository contains a comprehensive collection of API requests and responses, including authentication flows and data retrieval operations for blockchain and cryptocurrency-related services.

## Repository Structure

```
.
├── requests.json              # Main API request/response collection
├── LOGIN_STRUCTURE.md        # Login flow documentation
├── CONTENT_ANALYSIS.md       # Comprehensive API structure analysis
└── README.md                 # This file
```

## Quick Start

### Viewing the API Collection
The `requests.json` file contains all API requests in the following format:

```json
{
  "method": "HTTP_METHOD",
  "url": "API_ENDPOINT",
  "statusCode": STATUS_CODE,
  "headers": { /* Request headers */ },
  "payload": { /* Request body */ },
  "response": { /* Response body */ }
}
```

### Authentication
The collection includes login endpoints with both success and failure scenarios:

- **Login Success**: Status 200 with user data, tokens, and UI configuration
- **Login Failure**: Status 401 with error details and retry information

See [LOGIN_STRUCTURE.md](./LOGIN_STRUCTURE.md) for detailed authentication documentation.

## Features

### 1. Authentication System
- ✅ JWT-based authentication
- ✅ Access and refresh token management
- ✅ User profile data
- ✅ UI preferences and configuration
- ✅ Comprehensive error handling

### 2. Data Endpoints
- Trending cryptocurrency tokens
- Blockchain network information
- Token metadata and pricing
- Smart contract addresses
- Network configurations

### 3. Documentation
- Complete API structure analysis
- Security considerations
- Performance recommendations
- UI integration guidelines
- Best practices and patterns

## API Endpoints

### Authentication
- `POST /auth/login` - User authentication

### Data Retrieval
- `POST /chimpx/getTrendingTokens` - Fetch trending tokens
- `POST /relay/getChains` - Retrieve blockchain networks

## Documentation Files

### LOGIN_STRUCTURE.md
Comprehensive documentation of the login authentication flow including:
- Request/response structure for success and failure cases
- Token management
- UI configuration
- Security enhancements
- Implementation notes

### CONTENT_ANALYSIS.md
In-depth analysis of the API structure covering:
- Request structure templates
- Content patterns and consistency
- Security considerations
- Performance optimization recommendations
- Validation rules
- UI integration patterns

## Response Structure

### Success Response
```json
{
  "success": true,
  "message": "Operation successful",
  "data": {
    // Response data
  }
}
```

### Error Response
```json
{
  "success": false,
  "message": "Error message",
  "error": {
    "code": "ERROR_CODE",
    "type": "error_type",
    "details": "Detailed error information"
  },
  "ui": {
    "showError": true,
    "errorMessage": "User-friendly error message",
    "allowRetry": true,
    "retryDelay": 0
  }
}
```

## Security Features

- 🔒 JWT token-based authentication
- 🔒 Secure password handling (masked in documentation)
- 🔒 Proper HTTP status codes
- 🔒 Comprehensive error information without system exposure
- 🔒 Token expiration management
- 🔒 Refresh token support

## UI Integration

The API responses include UI-specific configuration:
- Redirect URLs after authentication
- Theme preferences (light/dark)
- Language settings
- Notification preferences
- Two-factor authentication status

## Development

### Validating JSON
```bash
python3 -m json.tool requests.json > /dev/null && echo "Valid JSON"
```

### Viewing Specific Requests
```bash
# View login requests only
jq '.[] | select(.url | contains("login"))' requests.json
```

## Contributing

When adding new API requests:
1. Follow the existing structure format
2. Include complete headers
3. Document both success and error cases
4. Add UI configuration where applicable
5. Update documentation files

## License

This project is for documentation and reference purposes.

## Support

For questions or issues, please refer to the documentation files:
- Login issues: See `LOGIN_STRUCTURE.md`
- API structure: See `CONTENT_ANALYSIS.md`

## Version History

- **v1.1** - Added login authentication structure with comprehensive documentation
- **v1.0** - Initial collection with trending tokens and chain data endpoints

## Fine-Tuning Adjustments

Recent improvements include:
- ✨ Complete login authentication flow (success/failure)
- ✨ JWT token management structure
- ✨ UI-ready response formats
- ✨ Comprehensive error handling
- ✨ Security enhancements
- ✨ Detailed documentation
- ✨ Content analysis and best practices

## Next Steps

Potential future enhancements:
- Add OAuth2 authentication flow
- Include rate limiting information
- Add pagination support
- Include caching strategies
- Add API versioning
- Implement request signing
- Add more endpoint examples
