---
title: 'Lição 2: Preparando a pasta de instantâneos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684657"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="7ab6c-102">Lição 2: Preparando a pasta do instantâneo</span><span class="sxs-lookup"><span data-stu-id="7ab6c-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="7ab6c-103">Nesta lição, você aprenderá a configurar a pasta do instantâneo, usada para criar e armazenar o instantâneo de publicação.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="7ab6c-104">Para criar um compartilhamento para a pasta de instantâneo e atribuir permissões</span><span class="sxs-lookup"><span data-stu-id="7ab6c-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="7ab6c-105">No Windows Explorer, vá para a pasta de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ab6c-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="7ab6c-106">O local padrão é C:\Arquivos de Programa\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="7ab6c-107">Crie uma nova pasta chamada **repldata**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="7ab6c-108">Clique com o botão direito do mouse nessa pasta e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7ab6c-109">Na guia **Compartilhamento** da caixa de diálogo **Propriedades de repldata** , clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="7ab6c-110">Na caixa de diálogo **Compartilhamento de Arquivos** , clique em **Compartilhar**e clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="7ab6c-111">Na guia **Segurança** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="7ab6c-112">Na caixa de diálogo **Permissões** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="7ab6c-113">Na caixa de texto **Selecionar usuário, computadores, conta de serviço ou grupos** , digite o nome da conta de agente de instantâneo criada na lição 1, como \<_Machine_Name> _**\ repl_snapshot**, em que \<*Machine_Name> \* é o nome do Publicador.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="7ab6c-114">Clique em **Verificar Nomes**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7ab6c-115">Repita a etapa anterior para adicionar permissões para o agente de distribuição, como \<_Machine_Name> _ **\ repl_distribution**, e para o agente de mesclagem como \<_Machine_Name> _ **\ repl_merge**.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="7ab6c-116">Verifique se as permissões a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="7ab6c-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="7ab6c-117">repl_snapshot - Controle total</span><span class="sxs-lookup"><span data-stu-id="7ab6c-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="7ab6c-118">repl_distribution - Leitura</span><span class="sxs-lookup"><span data-stu-id="7ab6c-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="7ab6c-119">repl_merge - Leitura</span><span class="sxs-lookup"><span data-stu-id="7ab6c-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="7ab6c-120">Clique em **OK** para fechar a caixa de diálogo **Propriedades de repldata** e criar o compartilhamento de repldata.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7ab6c-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7ab6c-121">Next Steps</span></span>  
 <span data-ttu-id="7ab6c-122">Você configurou com êxito o compartilhamento da pasta de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="7ab6c-123">A seguir, você configurará a distribuição.</span><span class="sxs-lookup"><span data-stu-id="7ab6c-123">Next, you will configure distribution.</span></span> <span data-ttu-id="7ab6c-124">Consulte [Lição 3: Configurando a distribuição](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="7ab6c-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab6c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ab6c-125">See Also</span></span>  
 [<span data-ttu-id="7ab6c-126">Proteger a pasta de instantâneos</span><span class="sxs-lookup"><span data-stu-id="7ab6c-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
