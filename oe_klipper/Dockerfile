ARG BUILD_FROM
FROM ${BUILD_FROM}

RUN echo 'import os, json, shutil' > /tmp/ip_check.py && \
    echo 'try:' >> /tmp/ip_check.py && \
    echo '    opts = json.load(open("/data/options.json"))' >> /tmp/ip_check.py && \
    echo '    printer_ip = opts.get("printer_ip", "")' >> /tmp/ip_check.py && \
    echo '    if printer_ip:' >> /tmp/ip_check.py && \
    echo '        os.environ["PRINTER_IP"] = printer_ip' >> /tmp/ip_check.py && \
    echo '    reset_pairing = str(opts.get("reset_pairing", False)).lower() == "true"' >> /tmp/ip_check.py && \
    echo '    last_ip = ""' >> /tmp/ip_check.py && \
    echo '    if os.path.exists("/data/.last_ip"):' >> /tmp/ip_check.py && \
    echo '        last_ip = open("/data/.last_ip").read().strip()' >> /tmp/ip_check.py && \
    echo '    if printer_ip and (printer_ip != last_ip or reset_pairing):' >> /tmp/ip_check.py && \
    echo '        print("====================================================")' >> /tmp/ip_check.py && \
    echo '        print(f"Neue IP ({last_ip} -> {printer_ip}) oder Reset aktiv! Loesche Daten...")' >> /tmp/ip_check.py && \
    echo '        print("====================================================")' >> /tmp/ip_check.py && \
    echo '        for item in os.listdir("/data"):' >> /tmp/ip_check.py && \
    echo '            if item != "options.json":' >> /tmp/ip_check.py && \
    echo '                p = os.path.join("/data", item)' >> /tmp/ip_check.py && \
    echo '                if os.path.isdir(p): shutil.rmtree(p, ignore_errors=True)' >> /tmp/ip_check.py && \
    echo '                else: os.remove(p)' >> /tmp/ip_check.py && \
    echo '        with open("/data/.last_ip", "w") as f:' >> /tmp/ip_check.py && \
    echo '            f.write(printer_ip)' >> /tmp/ip_check.py && \
    echo 'except Exception as e:' >> /tmp/ip_check.py && \
    echo '    print("Fehler im IP-Check:", e)' >> /tmp/ip_check.py && \
    echo '' >> /tmp/ip_check.py && \
    cat /app/octoeverywhere/docker_octoeverywhere/__main__.py >> /tmp/ip_check.py && \
    mv /tmp/ip_check.py /app/octoeverywhere/docker_octoeverywhere/__main__.py