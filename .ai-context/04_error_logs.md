# Error Logs

- **Phase 4 - Frontend Proxy Issue**: The frontend API requests were hitting the Vite dev server (`localhost:5173`) instead of the FastAPI backend. Resolved by configuring the proxy in `frontend/vite.config.js` to redirect `/api` calls to `http://127.0.0.1:8000`.
- **Phase 3 - passlib/bcrypt Incompatibility**: `passlib` crashed with newer versions of `bcrypt` (`AttributeError` / `ValueError` for 72 bytes wrap bug detection). Fixed by refactoring `utils/security.py` to use `bcrypt` directly, bypassing `passlib`.
- **Phase 6 - Vite Build Syntax Error**: Build failed due to unresolved imports (`../../../api/axiosClient`) in `AssetForm.jsx` and `AssetList.jsx`. Fixed by correcting relative paths to `../../api/axiosClient`.
- **Phase 9 - Vite Build Syntax Error**: Build failed due to unresolved imports (`../../../api/axiosClient`) in `Catalog.jsx`, `MyBookings.jsx`, and `BookingRequests.jsx`. Fixed by correcting relative paths to `../../api/axiosClient`.
