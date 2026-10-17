# syntax=docker/dockerfile:1.4
# Build context: this containers repository. Named context `app` points to laboratory-apps.
FROM node:22-alpine AS build
WORKDIR /app
COPY --from=app . ./
RUN npm install --no-audit --no-fund && npm run build

FROM nginx:1.27-alpine
COPY docker/angular/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/dist/laboratory/browser/ /usr/share/nginx/html/
EXPOSE 80
HEALTHCHECK --interval=30s --timeout=3s --start-period=10s CMD wget -q -O /dev/null http://127.0.0.1/ || exit 1
