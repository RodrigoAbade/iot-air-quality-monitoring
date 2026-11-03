# Segurança e configuração

## Credenciais

- Nunca publique `secrets.h`, tokens, senhas de Wi-Fi ou chaves privadas.
- Copie `secrets.example.h` para `secrets.h` localmente e configure os valores antes de compilar.
- O `.gitignore` impede novos commits acidentais de `secrets.h`, mas **não remove segredos do histórico**. Se alguma chave já foi publicada, revogue-a e gere outra.

## Atenção à comunicação de rede

O firmware atual usa `client.setInsecure()` no acesso HTTPS ao Supabase, desativando a validação do certificado. Isso é inadequado para produção e deve ser substituído por validação TLS adequada ao ESP8266.

O endpoint ThingSpeak está configurado com `http://`, sem criptografia de transporte. Antes de usar em produção, revise o suporte a HTTPS e as limitações do hardware.

## Escopo

Este projeto é um protótipo de monitoramento de qualidade do ar; suas classificações não equivalem a uma medição ambiental calibrada ou certificada.
