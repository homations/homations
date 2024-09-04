FROM "{{ keycloak_image_name }}:{{ keycloak_image_version }}" as builder

# Enable health and metrics support
# ENV KC_HEALTH_ENABLED=true
# ENV KC_METRICS_ENABLED=true

# Configure a database vendor
# ENV KC_DB="{{ keycloak_database_type }}"

WORKDIR /opt/keycloak
RUN /opt/keycloak/bin/kc.sh build --db="{{ keycloak_database_type }}"

FROM "{{ keycloak_image_name }}:{{ keycloak_image_version }}"
COPY --from=builder /opt/keycloak/ /opt/keycloak/

ENV KC_DB="{{ keycloak_database_type }}"
ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
