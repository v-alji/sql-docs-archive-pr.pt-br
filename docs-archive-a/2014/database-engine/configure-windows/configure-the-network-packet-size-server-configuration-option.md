---
title: Configurar a opção de configuração de servidor network packet size | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680623"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="5204c-102">Configurar a opção de configuração de servidor network packet size</span><span class="sxs-lookup"><span data-stu-id="5204c-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="5204c-103">Este tópico descreve como configurar a `network packet size` opção de configuração de servidor no usando o ou o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5204c-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5204c-104">A `network packet size` opção define o tamanho do pacote (em bytes) que é usado em toda a rede.</span><span class="sxs-lookup"><span data-stu-id="5204c-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="5204c-105">Os pacotes são partes de dados de tamanho fixo que transferem solicitações e resultados entre clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="5204c-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="5204c-106">O tamanho do pacote padrão é de 4.096 bytes.</span><span class="sxs-lookup"><span data-stu-id="5204c-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5204c-107">Não altere o tamanho do pacote a menos que você tenha certeza que melhorará o desempenho.</span><span class="sxs-lookup"><span data-stu-id="5204c-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="5204c-108">Para a maioria dos aplicativos, o tamanho do pacote padrão é o melhor.</span><span class="sxs-lookup"><span data-stu-id="5204c-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="5204c-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5204c-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5204c-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5204c-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5204c-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5204c-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5204c-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="5204c-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5204c-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="5204c-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5204c-114">**Para configurar a opção network packet size usando:**</span><span class="sxs-lookup"><span data-stu-id="5204c-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="5204c-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5204c-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5204c-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5204c-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5204c-117">**Acompanhamento:**  [depois de configurar a opção network packet size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5204c-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5204c-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5204c-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5204c-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5204c-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5204c-120">O tamanho máximo de pacote de rede para conexões criptografadas é 16.383 bytes.</span><span class="sxs-lookup"><span data-stu-id="5204c-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5204c-121">Recomendações</span><span class="sxs-lookup"><span data-stu-id="5204c-121">Recommendations</span></span>  
  
-   <span data-ttu-id="5204c-122">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5204c-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5204c-123">Se um aplicativo fizer operações de cópia em massa ou enviar ou receber grandes quantidades de texto ou dados de imagem, um tamanho do pacote maior que o padrão poderá melhorar a eficiência, porque resulta em menos operações de leitura e gravação em rede.</span><span class="sxs-lookup"><span data-stu-id="5204c-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="5204c-124">Se um aplicativo enviar e receber pequenas quantidades de informações, o tamanho do pacote poderá ser definido como 512 bytes, o que é suficiente para a maioria das transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="5204c-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="5204c-125">Nos sistemas que usam protocolos de rede diferentes, defina network packet size como o tamanho para o protocolo mais comum usado.</span><span class="sxs-lookup"><span data-stu-id="5204c-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="5204c-126">A opção network packet size melhora o desempenho da rede quando protocolos de rede oferecem suporte a pacotes maiores.</span><span class="sxs-lookup"><span data-stu-id="5204c-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="5204c-127">Aplicativos cliente podem substituir esse valor.</span><span class="sxs-lookup"><span data-stu-id="5204c-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="5204c-128">Você também pode chamar funções OLE DB, ODBC e DB-Library para solicitar uma alteração do tamanho do pacote.</span><span class="sxs-lookup"><span data-stu-id="5204c-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="5204c-129">Se o servidor não der suporte ao tamanho de pacote solicitado, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] enviará uma mensagem de aviso ao cliente.</span><span class="sxs-lookup"><span data-stu-id="5204c-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="5204c-130">Em algumas circunstâncias, alterar o tamanho de pacote pode conduzir a uma falha de link de comunicação, como esta:</span><span class="sxs-lookup"><span data-stu-id="5204c-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5204c-131">Segurança</span><span class="sxs-lookup"><span data-stu-id="5204c-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5204c-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="5204c-132">Permissions</span></span>  
 <span data-ttu-id="5204c-133">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="5204c-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5204c-134">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="5204c-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5204c-135">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="5204c-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5204c-136">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5204c-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="5204c-137">Para configurar a opção network packet size</span><span class="sxs-lookup"><span data-stu-id="5204c-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="5204c-138">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5204c-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5204c-139">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="5204c-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="5204c-140">Em **Rede**, selecione um valor para a caixa **Tamanho de Pacote de Rede** .</span><span class="sxs-lookup"><span data-stu-id="5204c-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5204c-141">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5204c-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="5204c-142">Para configurar a opção network packet size</span><span class="sxs-lookup"><span data-stu-id="5204c-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="5204c-143">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5204c-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5204c-144">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5204c-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5204c-145">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5204c-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5204c-146">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `network packet size` como `6500` bytes.</span><span class="sxs-lookup"><span data-stu-id="5204c-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="5204c-147">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5204c-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="5204c-148">Acompanhamento: depois de configurar a opção network packet size</span><span class="sxs-lookup"><span data-stu-id="5204c-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="5204c-149">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="5204c-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5204c-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5204c-150">See Also</span></span>  
 <span data-ttu-id="5204c-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5204c-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5204c-152">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5204c-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5204c-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5204c-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
