---
title: Logon para assinaturas atualizáveis | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684649"
---
# <a name="login-for-updatable-subscriptions"></a>Logon para Assinaturas Atualizáveis
  Se você selecionou **replicar** na página **assinaturas atualizáveis** desse assistente, deverá especificar uma conta no Assinante sob a qual as conexões com o Publicador são feitas para assinaturas de atualização imediata. Conexões são usadas pelos gatilhos acionados no Assinante e que propagam as alterações no Publicador. Essa conta é necessária mesmo se você selecionou **as alterações de fila e confirma quando possível** na página **assinaturas atualizáveis** , pois, por padrão, o assistente para nova assinatura configura a atualização em fila com a capacidade de alternar para a atualização imediata, se necessário.  
  
> [!IMPORTANT]  
>  A conta especificada para a conexão só deve receber permissão para inserir, atualizar e excluir dados nas exibições criadas pela replicação no banco de dados de publicação; nenhuma permissão adicional será dada. Conceda permissões nas exibições do banco de dados de publicação que são denominadas no formato **syncobj_** _\<HexadecimalNumber>_ para a conta configurada em cada Assinante.  
  
 Há três opções disponíveis para o tipo de conexão:  
  
-   Um servidor vinculado ou remoto que você já definiu.  
  
-   Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais que você especifica nesse assistente.  
  
-   Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais do usuário que faz a alteração no Assinante.  
  
 As duas primeiras opções podem ser especificadas nesse assistente. A última opção só pode ser especificada usando [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); Especifique um valor de **1** para o parâmetro **@security_mode** .  
  
## <a name="options"></a>Opções  
 **Criar um servidor vinculado que conecta usando o seguinte logon de Autenticação do SQL Server:**  
 A replicação cria um servidor vinculado usando as credenciais especificadas nos campos **Logon** e **Senha** .  
  
 **Logon**  
 Insira um logon [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tenha somente as permissões descritas neste tópico.  
  
 **Senha**  
 Insira uma senha forte para o logon especificado em **Logon**.  
  
 **Confirmar Senha**  
 Reinsira a senha para confirmar que ela foi inserida corretamente.  
  
 **Usar servidor vinculado ou remoto já definido.**  
 Essa opção requer um servidor vinculado ou remoto já definido. Para obter mais informações, consulte [Servidores vinculados &#40;Mecanismo de Banco de Dados&#41;](../linked-servers/linked-servers-database-engine.md) e [Servidores remotos](../../database-engine/configure-windows/remote-servers.md). Verifique se o logon usado para o servidor vinculado ou servidor remoto tem uma senha forte e somente as permissões descritas nesse tópico.  
  
## <a name="see-also"></a>Consulte Também  
 [Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md)   
 [Exibir e modificar configurações de segurança de replicação](security/view-and-modify-replication-security-settings.md)   
 [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md)   
 [Assinar publicações](subscribe-to-publications.md)  
  
  
