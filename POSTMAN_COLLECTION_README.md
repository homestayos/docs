# HomestayOS API Postman Collection

This directory contains a complete Postman collection for the HomestayOS API, generated from the Mintlify documentation and OpenAPI specification.

## Files

- `HomestayOS_API.postman_collection.json` - Complete Postman collection with all API endpoints
- `HomestayOS_API.postman_environment.json` - Postman environment file with variables
- `POSTMAN_COLLECTION_README.md` - This file

## Quick Start

### 1. Import the Collection

1. Open Postman
2. Click **Import** button
3. Select `HomestayOS_API.postman_collection.json`
4. Click **Import**

### 2. Import the Environment (Optional but Recommended)

1. Click **Import** button
2. Select `HomestayOS_API.postman_environment.json`
3. Click **Import**
4. Select the imported environment from the environment dropdown (top right)

### 3. Set Up Authentication

The collection supports two authentication methods:

#### Option A: Bearer Token (User Sessions)

1. Use the **Login** endpoint in the Authentication folder
2. Enter your email and password
3. The collection automatically saves the token to the `auth_token` variable
4. All subsequent requests will use this token automatically

#### Option B: API Key (Programmatic Access)

1. Create an API key using the **Create API Key** endpoint in the Developer folder
2. Copy the API key from the response
3. Set the `api_key` variable in your environment:
   - Click on the environment name
   - Edit the `api_key` variable
   - Paste your API key
   - Save

**Note:** For API Key authentication, you'll need to modify the Authorization header in requests from `Bearer {{auth_token}}` to use `X-API-Key: {{api_key}}` instead.

## Collection Structure

The collection is organized into the following folders:

### Authentication
- Login
- Register
- Logout
- Forgot Password
- Reset Password
- Get Current User

### Dashboard
- Get Dashboard

### Properties
- List Properties
- Create Property
- Get Property
- Update Property
- Delete Property
- Get Property Availability

### Bookings
- List Bookings
- Create Booking
- Get Booking
- Update Booking
- Cancel Booking

### Guests
- List Guests
- Create Guest
- Get Guest
- Update Guest
- Get Guest Statistics

### Calendar
- Get Calendar URL

### Analytics
- Get Revenue Analytics
- Get Occupancy Analytics

### Conversations
- List Conversations
- Create Conversation
- Send Message

### Tasks
- List Tasks
- Create Task
- Update Task Status

### Maintenance
- List Maintenance Requests
- Create Maintenance Request
- Get Maintenance Request
- Update Maintenance Request
- Update Maintenance Status
- Delete Maintenance Request
- Get Maintenance Statistics
- List Maintenance Automations
- Create Maintenance Automation
- Get Maintenance Automation
- Update Maintenance Automation
- Delete Maintenance Automation

### Developer
- List API Keys
- Create API Key
- List Webhook Subscriptions
- Create Webhook Subscription
- Get Available Webhook Events

## Environment Variables

The collection uses the following variables:

| Variable | Description | Default Value |
|----------|-------------|---------------|
| `base_url` | API base URL | `https://office.homestayos.com/api` |
| `auth_token` | Bearer token for authentication | (empty, set after login) |
| `api_key` | API key for programmatic access | (empty, set manually) |
| `tenant_slug` | Optional tenant slug | (empty) |

## Features

### Automatic Token Management
The Login endpoint includes a test script that automatically saves the authentication token to the `auth_token` collection variable. This token is then used by all authenticated endpoints.

### Pre-filled Examples
All requests include example data in the request body, making it easy to test endpoints without manually entering data.

### Query Parameters
List endpoints include pre-configured query parameters with descriptions. You can modify or remove these as needed.

### Path Variables
Endpoints that require IDs (like `/properties/:id`) use Postman path variables. You can set these in the URL or use the variable editor.

## Usage Tips

1. **Start with Login**: Always authenticate first using the Login endpoint before making other requests.

2. **Use Environment Variables**: Create different environments for development, staging, and production by duplicating the environment file and changing the `base_url`.

3. **Modify Request Bodies**: All request bodies include example data. Modify these to match your actual data.

4. **Check Responses**: Review the response structure to understand the API's data format.

5. **Use Collection Runner**: You can use Postman's Collection Runner to run multiple requests in sequence, useful for testing workflows.

## Switching Between Authentication Methods

### Using Bearer Token
- Use the Login endpoint to get a token
- Token is automatically saved to `auth_token` variable
- All requests use `Authorization: Bearer {{auth_token}}` header

### Using API Key
1. Create an API key using the Developer endpoints
2. Set the `api_key` environment variable
3. For each request, change the Authorization header from:
   ```
   Authorization: Bearer {{auth_token}}
   ```
   to:
   ```
   X-API-Key: {{api_key}}
   ```

## Troubleshooting

### 401 Unauthorized
- Make sure you've logged in and the token is saved
- Check that the `auth_token` variable is set
- Verify the token hasn't expired (tokens may expire after a period of inactivity)

### 404 Not Found
- Verify the `base_url` is correct
- Check that the endpoint path is correct
- Ensure path variables (like `:id`) are set correctly

### 422 Unprocessable Entity
- Check the request body format
- Verify all required fields are included
- Check field types match the API requirements

## Updating the Collection

This collection is generated from the OpenAPI specification. To update:

1. Update the OpenAPI spec at `/docs/api-reference/openapi.json`
2. Regenerate the Postman collection using a tool like [openapi-to-postman](https://github.com/postmanlabs/openapi-to-postman) or manually update the collection

## Support

For API support:
- **Email**: homestayos.com@gmail.com
- **Documentation**: See the Mintlify documentation at `/docs/api-reference/`

## License

This collection is provided as-is for use with the HomestayOS API.

