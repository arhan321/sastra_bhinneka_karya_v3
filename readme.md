## Jika terjadi error vite
```
apt-get update && \
apt-get install -y curl ca-certificates gnupg && \
curl -fsSL https://deb.nodesource.com/setup_22.x -o /tmp/nodesource_setup.sh && \
bash /tmp/nodesource_setup.sh && \
apt-get install -y nodejs && \
rm -f /tmp/nodesource_setup.sh && \
cd /var/www/html && \
node -v && \
npm -v && \
if [ -f package-lock.json ]; then npm ci; else npm install; fi && \
npm run build && \
ls -lah public/build/manifest.json && \
php artisan optimize:clear
```