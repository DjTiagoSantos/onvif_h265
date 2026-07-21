# ONVIF H265/H265+ Integration

Uma integração personalizada para Home Assistant que estende a integração oficial ONVIF para suportar os codecs de vídeo **H.265 (HEVC)** e **H.265+**.

## Por que esta integração?

A integração oficial ONVIF do Home Assistant só suporta o codec H.264 (AVC) e filtra qualquer perfil de câmera que não seja H.264. Esta integração modifica esse comportamento para aceitar streams H.264, H.265 (HEVC) e H.265+, permitindo o uso de câmeras modernas que exigem esses codecs de maior eficiência.

## Requisitos

- ONVIF habilitado e acessível na câmera
- A câmera deve anunciar perfis H.264, H.265 ou H.265+ na resposta GetProfiles
- Home Assistant 2024.1.0 ou mais recente

## Observações sobre H.265

- **Suporte em navegadores:** o H.265 não é amplamente suportado em navegadores web. Considere usar o app mobile do Home Assistant (iOS/Android) para melhor experiência.
- **Transcodificação:** ao acessar pelo navegador, o Home Assistant (via FFmpeg) pode precisar transcodificar o stream H.265 para H.264 em tempo real, o que pode consumir bastante CPU.

---

Consulte o [README](README.md) completo para instruções detalhadas de instalação e configuração.
