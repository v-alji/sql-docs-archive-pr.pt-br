---
title: Adicionar ou substituir uma testemunha de espelhamento de banco de dados (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571590"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="ff739-102">Adicionar ou substituir uma testemunha de espelhamento de banco de dados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ff739-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ff739-103">Se os pontos de extremidade do espelhamento de banco de dados usar Autenticação do Windows, você poderá usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para adicionar ou substituir uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="ff739-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="ff739-104">Ao adicionar uma testemunha ao [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] isso também altera o modo operacional para modo de segurança alta com failover automático.</span><span class="sxs-lookup"><span data-stu-id="ff739-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff739-105">É altamente recomendável que a testemunha resida em um computador diferente do dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="ff739-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="ff739-106">A conta de serviço usada pela testemunha deve estar no mesmo domínio que as contas de serviço usadas pelas instâncias do servidor principal e espelho ou deve estar em um domínio confiável.</span><span class="sxs-lookup"><span data-stu-id="ff739-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="ff739-107">Para adicionar ou substitui uma testemunha</span><span class="sxs-lookup"><span data-stu-id="ff739-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="ff739-108">Depois de se conectar à instância do servidor principal, no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="ff739-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ff739-109">Expanda **Bancos de Dados**e selecione o banco de dados principal da sessão para a qual você está adicionando ou substituindo uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="ff739-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="ff739-110">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="ff739-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="ff739-111">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ff739-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="ff739-112">Clique em **Configurar Segurança**.</span><span class="sxs-lookup"><span data-stu-id="ff739-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="ff739-113">Se a tela de boas-vindas do **Assistente para Configurar Segurança de Espelhamento de Banco de Dados** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ff739-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ff739-114">Na caixa de diálogo **Incluir Servidor Testemunha** , clique em **Sim**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ff739-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="ff739-115">Na caixa de diálogo **Selecionar Servidores a Serem Configurados** , a caixa de seleção **Instância do servidor testemunha** é marcada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ff739-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="ff739-116">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ff739-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="ff739-117">Na caixa de diálogo **Instância do Servidor Principal** mantenha a porta e o ponto de extremidade existentes.</span><span class="sxs-lookup"><span data-stu-id="ff739-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="ff739-118">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ff739-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ff739-119">Na caixa de diálogo **Instância do Servidor Testemunha** , clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ff739-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="ff739-120">Na caixa de diálogo **Conectar ao Servidor** , especifique a instância de servidor testemunha no campo **Nome do servidor** e use Autenticação do Windows (o padrão).</span><span class="sxs-lookup"><span data-stu-id="ff739-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="ff739-121">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ff739-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="ff739-122">Quando uma conexão é estabelecida, a porta do ouvinte e o ponto de extremidade do espelhamento de banco de dados da instância do servidor testemunha são exibidos na caixa de diálogo **Instância do Servidor Testemunha** .</span><span class="sxs-lookup"><span data-stu-id="ff739-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="ff739-123">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ff739-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="ff739-124">A caixa de diálogo **Contas de Serviço** contém campos para as contas de serviço de domínio das instâncias de servidor principal, espelho e testemunha.</span><span class="sxs-lookup"><span data-stu-id="ff739-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="ff739-125">Se as instâncias de servidor usarem todas a mesma conta de serviço, deixe os campos em branco.</span><span class="sxs-lookup"><span data-stu-id="ff739-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="ff739-126">Se a instância do servidor testemunha usar uma conta de serviço diferente de qualquer um dos parceiros, preencha os campos **Principal**, **Espelho**e **Testemunha** com o nome de conta:</span><span class="sxs-lookup"><span data-stu-id="ff739-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="ff739-127">*DOMAINNAME* **\\** *username*</span><span class="sxs-lookup"><span data-stu-id="ff739-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="ff739-128">O nome de domínio deve estar em maiúscula.</span><span class="sxs-lookup"><span data-stu-id="ff739-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="ff739-129">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ff739-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="ff739-130">Opcionalmente, na tela de resumo **Concluir o Assistente** , verifique a configuração de testemunha e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ff739-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="ff739-131">Ao terminar, o assistente o leva de volta para a caixa de diálogo **Propriedades do Banco de Dados** , em que agora o endereço de rede do servidor da testemunha aparece no campo **Testemunha** .</span><span class="sxs-lookup"><span data-stu-id="ff739-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="ff739-132">Além disso, **High-safety mode with automatic failover (synchronous) (Modo de segurança alta com failover automático (síncrono))** , que é exigido com uma testemunha, é selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ff739-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="ff739-133">Para habilitar a testemunha e alterar a sessão para o modo de segurança alta com failover automático, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff739-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff739-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff739-134">See Also</span></span>  
 <span data-ttu-id="ff739-135">[Testemunha de espelhamento de banco de dados](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="ff739-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="ff739-136">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ff739-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="ff739-137">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="ff739-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="ff739-138">[Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="ff739-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="ff739-139">Testemunha de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ff739-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
