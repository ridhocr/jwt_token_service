# JwtTokenHelper

**JwtTokenHelper** adalah library sederhana untuk membantu generate dan validasi JWT Token di .NET 8.

🛡️ Mendukung:
- Algoritma HMAC SHA256
- Validasi dengan issuer & audience
- Claim custom

## 🔧 Cara Install

```bash
dotnet add package NeliCompany.JwtTokenHelper

🚀 Cara Pakai
var jwtService = new JwtTokenService(
    secretKey: "my_super_secret_key",
    issuer: "my-app",
    audience: "my-users"
);

var claims = new Dictionary<string, string>
{
    { ClaimTypes.NameIdentifier, "123" },
    { ClaimTypes.Email, "user@email.com" }
};

string token = jwtService.GenerateToken(claims);

var validated = jwtService.ValidateToken(token);

if (validated != null)
{
    Console.WriteLine("Token valid!");
}
else
{
    Console.WriteLine("Token tidak valid.");
}
