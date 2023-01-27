# npm-linked-slow-install

## Steps to reproduce

1. `npm install` (to prime the local cache)
2. `rm -rf node_modules && time npm install --install-strategy=linked`
3. `time npm install --install-strategy=linked`
4. `rm -rf node_modules && time npm install`
5. `time npm install`

## Results

- `npm install --install-strategy=linked` first run: `15.98s user 7.19s system 149% cpu 15.535 total`
- `npm install --install-strategy=linked` second run: `17.87s user 8.47s system 151% cpu 17.407 total`
- `npm install` first run: `11.83s user 5.80s system 141% cpu 12.495 total`
- `npm install` second run: `2.52s user 0.15s system 120% cpu 2.207 total`
