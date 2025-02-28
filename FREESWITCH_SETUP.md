# FreeSWITCH Developer Job Specification

## **Project Requirements**

The SIP GOAL UC project requires a **fully configured FreeSWITCH server** with all necessary and potentially useful modules installed. The server must be **efficient, secure, and stable** while allowing for **easy customization** if additional modules are needed in the future.

This document outlines the key points to cover and document the FreeSWITCH setup in a MD file.

---

## **1. Required FreeSWITCH Modules**

All the following modules must be installed to support SIP GOAL UC. The setup should also allow for **future module adjustments** if necessary.

### **Essential Modules**

- **Core Functionality:**
  - `mod_sofia` (SIP signaling)
  - `mod_loopback` (Internal call routing)
  - `mod_conference` (Multi-party conferencing)
  - `mod_db` (Database interaction)
  - `mod_dptools` (Dialplan tools)
  - `mod_commands` (Basic FreeSWITCH commands)

- **Call Handling & Routing:**
  - `mod_fifo` (Call queue management)
  - `mod_valet_parking` (Call parking)
  - `mod_enum` (ENUM-based call routing)

- **Logging & Event Handling:**
  - `mod_event_socket` (External event handling)
  - `mod_cdr_pg_csv` (PostgreSQL CDR logging)
  - `mod_logfile` (Call logging)

- **Codec Support:**
  - `mod_opus`
  - `mod_g729`
  - `mod_g723_1`
  - `mod_h26x` (Video codecs if needed)

- **IVR & Scripting:**
  - `mod_lua` (For IVR scripting)
  - `mod_sms` (SMS handling if required)

- **Security & Monitoring:**
  - `mod_hash` (Security & authentication support)
  - `mod_spandsp` (Fax and DTMF handling)

The setup must allow **easy customization** so additional modules can be installed or removed as needed.

---

## **2. Security Hardening**

Security is critical for SIP GOAL UC. The developer must:

- **Restrict Network Access:**
  - Bind FreeSWITCH to **specific IP addresses**.
  - Enable **only SIP (UDP, TCP, and TLS as needed)**.

- **Disable Unused Services:**
  - Ensure that **only required modules** are loaded.

- **Secure Database Connection:**
  - The **PostgreSQL database is remote**—the developer will be given dummy credentials for setup, which will be replaced later.

- **Development vs. Production Setup:**
  - Enable **detailed logging and debugging** on the development server.
  - Ensure **logging is enabled** for debugging but disable unnecessary debug tools in production.

---

## **3. Optimization & Stability**

The FreeSWITCH setup must be **optimized for SIP-based call automation**.

### **Performance Tuning:**

- **Optimize Sofia-SIP Settings:**
  - Adjust **SIP timers, NAT handling, and registration timeouts**.
  - Enable **asynchronous processing for call handling**.

- **Tune Threading & Resource Allocation:**
  - Adjust **worker threads based on server CPU**.
  - Optimize **memory usage and garbage collection**.

- **Logging & Monitoring:**
  - Configure **log rotation** to prevent excessive disk usage.
  - Ensure **real-time monitoring of call activity**.

---

## **4. Deliverables**

The developer must provide:

1. A **fully configured FreeSWITCH server** with all required modules installed and optimized.
2. A **detailed MD file** documenting the entire setup process, including:
   - Exact installation steps.
   - Configuration changes.
   - Security and optimization details.

This setup must be **production-ready** while allowing for future modifications.

---

## **Final Notes**

The developer must ensure:

- **All required modules are installed.**
- **Security best practices are followed.**
- **The setup is well-documented for future modifications.**
