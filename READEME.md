# WooCommerce Integration API

Laravel 11 REST API for WooCommerce product management with real-time synchronization.

## Quick Start

1. **Clone & Install**
   ```bash
   git clone git@github.com:kishoresingh0/WooCommerce-Integration-API.git
   cd <project-directory>
   composer install
   cp .env.example .env

2. **Configure WooCommerce in .env:**
 
    WOOCOMMERCE_STORE_URL=https://b2b.xtraprotein.com/
    WOOCOMMERCE_CONSUMER_KEY=ck_c3bd4960eedd079eaa170be864d29928ffc918e2
    WOOCOMMERCE_CONSUMER_SECRET=cs_497154ed004bc4f0e21af60f5292d87eb4f4d93b
    WC_VERSION=wc/v3

3. **Run Server**
    php artisan serve

4. **API Endpoints**

    Base URL: http://127.0.0.1:8000/api/woocommerce
    
    Method	        Endpoint	        Description

    GET	            /products	        Get all products
    POST	        /products	        Create new product
    PUT	            /products/{id}	    Update product
    DELETE	        /products/{id}	    Delete product
    POST	        /sync	            Sync products to local DB

    Example Usage

    Create Product: 

    curl -X POST http://127.0.0.1:8000/api/woocommerce/products \
    -H "Content-Type: application/json" \
    -d '{
        "name": "Test Product",
        "sku": "TEST123",
        "price": 99.99,
        "quantity": 10
    }'

    Sync Products: 

    curl -X POST http://127.0.0.1:8000/api/woocommerce/sync

5. **Requirements**
        PHP 8.1+, Laravel 11
        WooCommerce store with REST API enabled
        Valid Consumer Key/Secret

6. **Response Format:**

    All endpoints return JSON responses with appropriate HTTP status codes:
    200 Success
    201 Created
    400 Bad Request
    404 Not Found
    500 Server Error

7. **Error Handling:**

    The API returns standardized error responses:
    {
        "error": "Error message description",
        "code": "HTTP_STATUS_CODE"
    }

8. **Testing :**

    You can test the API using:
    cURL commands (examples provided above)
    Postman
    Any HTTP client

9. **Features**

    ✅ Full CRUD operations
    ✅ Real-time WooCommerce sync
    ✅ Background job processing
    ✅ Request validation & error handling
    ✅ Comprehensive logging

10. **Notes:**

    Ensure your WooCommerce store has REST API enabled
    Verify consumer key/secret have appropriate permissions
    The API handles rate limiting according to WooCommerce's policies
    All product operations are reflected in your WooCommerce admin dashboard

11. **Postman:**    
    API collection to file Wo Comm.postman_collection.json
