# RustDesk Connection Transfer Guide

## Introdução
Este repositório documenta minhas experiências e descobertas ao aprender a usar o RustDesk para transferir conexões entre diferentes PCs. Aqui, você encontrará informações sobre a configuração inicial, as melhores práticas para transferir conexões e considerações de segurança.

## Configuração Inicial
Hoje, comecei a trabalhar com o RustDesk e consegui criar um contêiner Docker, configurando o firewall e o acesso remoto. A conexão está boa e responsiva, o que é encorajador para futuras implementações.

## Desafios Encontrados
Um dos desafios que enfrentei foi a ausência de um livro de endereços centralizado ou um sistema de login para gerenciar IDs e senhas remotas. Embora seja possível renomear e adicionar conexões aos favoritos, essa funcionalidade é local e não atende à necessidade de acesso desatendido.

### Transferindo Conexões
Para transferir todas as conexões para outro PC, a melhor prática identificada até agora é copiar os seguintes arquivos:

- `C:\Users\%username%\AppData\Roaming\RustDesk\config`
- `peers`
- `RustDesk_local.toml`

É importante notar que não é aconselhável simplesmente replicar toda a pasta `AppData`, pois o arquivo `RustDesk.toml` contém configurações específicas do cliente local.

## Considerações de Segurança
Uma preocupação significativa é que muitas informações sensíveis na pasta `AppData` estão armazenadas em texto claro, incluindo a chave RSA do servidor, IDs de conexão e senhas salvas. Após uma análise mais aprofundada, descobri que as senhas das conexões salvas são hashadas, mas a senha do cliente permanece em texto claro.

### Melhores Práticas
Para garantir uma transferência bem-sucedida das conexões:
1. **Certifique-se de que o RustDesk esteja fechado** antes de copiar os arquivos.
2. **Replicar os arquivos** `peers` e `RustDesk_local.toml` funcionou corretamente em meus testes.

## Futuras Melhorias
Estou ansioso para ver melhorias no RustDesk, como um livro de endereços centralizado que armazene informações de conexão em um servidor com suporte a login com 2FA. Isso não apenas aumentaria a conveniência do armazenamento centralizado, mas também melhoraria a segurança geral da aplicação.

## Conclusão
Continuarei explorando o RustDesk e documentando minhas descobertas. Espero que este guia ajude outros usuários a navegar pelos desafios de transferência de conexões e segurança no uso do RustDesk. Fique à vontade para contribuir com suas próprias experiências ou sugestões!

---

Sinta-se à vontade para adicionar mais informações ou ajustes conforme necessário!
