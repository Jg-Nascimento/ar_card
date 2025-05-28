# Guia de Uso - Cartão AR para Dispositivos Móveis

Este documento fornece instruções detalhadas sobre como configurar, hospedar e utilizar o protótipo WebAR para cartões de visita.

## Conteúdo do Projeto

- `index.html`: Página principal da experiência WebAR
- `assets/marker.png`: Imagem do cartão que serve como marcador AR
- `assets/icons/`: Ícones SVG para redes sociais
- `assets/video.mp4`: Vídeo de apresentação (você precisará adicionar seu próprio vídeo)

## Requisitos para Hospedagem

Para que a experiência WebAR funcione corretamente, o site deve ser hospedado em um servidor HTTPS. Isso é um requisito de segurança dos navegadores para acessar a câmera.

### Opções de Hospedagem

1. **GitHub Pages (Recomendado para testes)**
   - Gratuito e fácil de configurar
   - Suporta HTTPS automaticamente
   - Ideal para projetos de demonstração

2. **Netlify, Vercel ou Firebase Hosting**
   - Opções gratuitas com recursos avançados
   - Configuração simples com integração contínua
   - Bom para projetos em produção

3. **Servidor Web próprio**
   - Requer certificado SSL/TLS para HTTPS
   - Maior controle sobre a infraestrutura
   - Recomendado para implementações corporativas

## Passos para Hospedagem no GitHub Pages

1. Crie um repositório no GitHub
2. Faça upload de todos os arquivos do projeto
3. Vá para "Settings" > "Pages"
4. Selecione a branch principal (geralmente "main") como fonte
5. Clique em "Save" e aguarde alguns minutos
6. O GitHub fornecerá uma URL (geralmente `https://seuusuario.github.io/seurepo/`)

## Criação do QR Code para o Cartão

1. Acesse um gerador de QR Code online (como qr-code-generator.com)
2. Insira a URL da sua página WebAR hospedada
3. Baixe o QR Code gerado
4. Adicione o QR Code ao design do seu cartão de visita

## Preparação do Cartão de Visita

1. **Design do Cartão**:
   - Inclua a imagem do marcador (a mesma usada no código)
   - Adicione o QR Code que direciona para a URL da experiência AR
   - Inclua instruções simples como "Escaneie para experiência AR"

2. **Impressão**:
   - Use papel de boa qualidade para melhor reconhecimento do marcador
   - Evite acabamentos muito brilhantes que possam causar reflexos
   - Mantenha o tamanho do marcador com pelo menos 5cm x 5cm para melhor detecção

## Como Usar a Experiência AR

### Para o Proprietário do Cartão

1. Compartilhe seu cartão físico com contatos
2. Explique que o cartão possui recursos de AR acessíveis via smartphone
3. Atualize os links e conteúdos conforme necessário editando os arquivos e republicando

### Para Quem Recebe o Cartão

1. Escaneie o QR Code com a câmera do smartphone
2. Permita o acesso à câmera quando solicitado pelo navegador
3. Aponte a câmera para o cartão de visita
4. Quando o marcador for detectado, o conteúdo AR aparecerá
5. Toque nos ícones de redes sociais para acessar os perfis

## Personalização do Conteúdo

### Vídeo de Apresentação

1. Crie um vídeo curto (15-30 segundos) em formato MP4
2. Substitua o arquivo `assets/video.mp4` pelo seu vídeo
3. Mantenha o tamanho do arquivo abaixo de 5MB para carregamento rápido

### Links de Redes Sociais

Edite o arquivo `index.html` e localize as seguintes linhas:

```html
event-set__click="_event: click; _target: #whatsapp-button; url: https://wa.me/5599999999999"
```

```html
event-set__click="_event: click; _target: #instagram-button; url: https://instagram.com/seuperfil"
```

```html
event-set__click="_event: click; _target: #linkedin-button; url: https://linkedin.com/in/seuperfil"
```

Substitua as URLs pelos seus próprios links.

### Informações de Contato

Localize a div com id "arInfo" e atualize com suas informações:

```html
<div class="ar-info" id="arInfo">
    JN Tecnologia<br>
    contato@jntecnologia.com.br
</div>
```

## Dicas para Testes

1. **Teste em Diferentes Dispositivos**:
   - Android e iOS têm comportamentos diferentes com WebAR
   - Teste em dispositivos mais antigos para garantir compatibilidade

2. **Condições de Iluminação**:
   - O reconhecimento do marcador funciona melhor em ambientes bem iluminados
   - Evite reflexos diretos no cartão

3. **Distância e Ângulo**:
   - Mantenha o cartão a uma distância de 20-40cm da câmera
   - Evite ângulos muito inclinados para melhor detecção

4. **Conexão de Internet**:
   - A primeira carga pode ser mais lenta dependendo da conexão
   - Após o primeiro carregamento, o navegador pode armazenar em cache

## Solução de Problemas

1. **Câmera não inicializa**:
   - Verifique se o site está sendo acessado via HTTPS
   - Confirme que as permissões de câmera foram concedidas no navegador

2. **Marcador não é detectado**:
   - Melhore a iluminação do ambiente
   - Evite cobrir partes do marcador com os dedos
   - Verifique se o marcador impresso está nítido e sem distorções

3. **Vídeo não reproduz**:
   - Em iOS, o vídeo pode precisar de interação do usuário para iniciar
   - Verifique se o formato do vídeo é compatível (MP4 é recomendado)

4. **Botões não respondem ao toque**:
   - Alguns navegadores móveis tratam eventos de toque diferentemente
   - Tente tocar e segurar brevemente em vez de toques rápidos
