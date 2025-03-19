# MySQL MCP Server

A Model Context Protocol (MCP) server that enables secure interaction with MySQL databases. This server allows AI assistants to list tables, read data, and execute SQL queries through a controlled interface, making database exploration and analysis safer and more structured.

## Features

- List available MySQL tables as resources
- Read table contents
- Execute SQL queries with proper error handling
- Secure database access through environment variables
- Comprehensive logging

## Installation

```bash
git clone https://github.com/he426100/mysql-mcp-server
cd mysql-mcp-server
composer install
```

## Configuration

Set the following environment variables:

```bash
DB_HOST=localhost     # Database host
DB_PORT=3306         # Optional: Database port (defaults to 3306 if not specified)
DB_USERNAME=your_username
DB_PASSWORD=your_password
DB_DATABASE=your_database
```

## Usage


### As a standalone server

```bash
# Install dependencies
composer install

# Run the server
php bin/console
```

### docker

```bash
docker build -t mysql-mcp-server .
docker run -i --rm mysql-mcp-server --host 127.0.0.1
```

## Security Considerations

- Never commit environment variables or credentials
- Use a database user with minimal required permissions
- Consider implementing query whitelisting for production use
- Monitor and log all database operations

## Security Best Practices

This MCP server requires database access to function. For security:

1. **Create a dedicated MySQL user** with minimal permissions
2. **Never use root credentials** or administrative accounts
3. **Restrict database access** to only necessary operations
4. **Enable logging** for audit purposes
5. **Regular security reviews** of database access

See [MySQL Security Configuration Guide](https://github.com/he426100/mysql-mcp-server/blob/main/SECURITY.md) for detailed instructions on:
- Creating a restricted MySQL user
- Setting appropriate permissions
- Monitoring database access
- Security best practices

⚠️ IMPORTANT: Always follow the principle of least privilege when configuring database access.

## Credits

[mysql_mcp_server](https://github.com/designcomputer/mysql_mcp_server/) .

## License

MIT License - see LICENSE file for details.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
