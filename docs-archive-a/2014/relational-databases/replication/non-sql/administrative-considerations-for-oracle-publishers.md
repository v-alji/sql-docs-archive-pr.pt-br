---
title: Considerações administrativas sobre Publicadores Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576283"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="471b3-102">Considerações administrativas sobre Oracle Publishers</span><span class="sxs-lookup"><span data-stu-id="471b3-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="471b3-103">Após configurar um Editor Oracle e ativar os mecanismos de rastreamento de alterações de replicação, os administradores do sistema de banco de dados Oracle ainda podem usar os utilitários de banco de dados padrão Oracle e realizar tarefas típicas de administração de sistemas.</span><span class="sxs-lookup"><span data-stu-id="471b3-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="471b3-104">Porém, você deve estar ciente quanto aos efeitos que a execução de certas tarefas administrativas pode ter nos dados publicados.</span><span class="sxs-lookup"><span data-stu-id="471b3-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="471b3-105">Com exceção de descartar ou modificar uma coluna publicada para replicação e descartar ou modificar qualquer objeto de replicação, essas considerações não se aplicam à publicação de instantâneos.</span><span class="sxs-lookup"><span data-stu-id="471b3-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="471b3-106">Importando e carregando dados</span><span class="sxs-lookup"><span data-stu-id="471b3-106">Importing and loading data</span></span>  
 <span data-ttu-id="471b3-107">Gatilhos são usados para rastrear alterações em publicações transacionais no Oracle.</span><span class="sxs-lookup"><span data-stu-id="471b3-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="471b3-108">As alterações em tabelas publicadas podem ser replicadas para os Assinantes apenas se os gatilhos de replicação forem acionados quando ocorrer uma atualização, uma inserção ou uma exclusão.</span><span class="sxs-lookup"><span data-stu-id="471b3-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="471b3-109">Os utilitários Oracle Import e SQL\*Loader, da Oracle, têm opções que afetam o acionamento dos gatilhos quando linhas são inseridas em tabelas replicadas com esses utilitários.</span><span class="sxs-lookup"><span data-stu-id="471b3-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="471b3-110">Oracle Import</span><span class="sxs-lookup"><span data-stu-id="471b3-110">Oracle Import</span></span>  
 <span data-ttu-id="471b3-111">Com o Oracle Import, é possível definir a opção **ignorar** para 's' ou 'n' (o padrão é 'n').</span><span class="sxs-lookup"><span data-stu-id="471b3-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="471b3-112">Se **ignorar** for definido como 'n', a tabela será descartada e recriada durante a importação.</span><span class="sxs-lookup"><span data-stu-id="471b3-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="471b3-113">Isso remove os gatilhos de replicação e desabilita a replicação.</span><span class="sxs-lookup"><span data-stu-id="471b3-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="471b3-114">Se **ignorar** for definido como 's', a importação tentará carregar as linhas na tabela existente, o que aciona os gatilhos de replicação.</span><span class="sxs-lookup"><span data-stu-id="471b3-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="471b3-115">Portanto, certifique-se de que **ignorar** esteja definido como 's' ao importar para uma tabela replicada com a ferramenta de importação.</span><span class="sxs-lookup"><span data-stu-id="471b3-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="471b3-116">SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="471b3-116">SQL\*Loader</span></span>  
 <span data-ttu-id="471b3-117">Com o SQL\*Loader, você pode definir a opção **direto** como 'true' ou 'false' (o padrão é 'false').</span><span class="sxs-lookup"><span data-stu-id="471b3-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="471b3-118">Se **direcionar** estiver definido como 'falso', serão inseridas linhas usando instruções convencionais INSERT que acionam gatilhos de replicação.</span><span class="sxs-lookup"><span data-stu-id="471b3-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="471b3-119">Se **direcionar** estiver definido como 'verdadeiro', a carga será otimizada e os gatilhos não serão acionados.</span><span class="sxs-lookup"><span data-stu-id="471b3-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="471b3-120">Portanto, certifique-se de que **direcionar** esteja definido como 'falso' ao importar para uma tabela replicada com a ferramenta SQL\*Loader.</span><span class="sxs-lookup"><span data-stu-id="471b3-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="471b3-121">Fazendo alterações em objetos publicados</span><span class="sxs-lookup"><span data-stu-id="471b3-121">Making changes to published objects</span></span>  
 <span data-ttu-id="471b3-122">As seguintes ações não requerem nenhuma consideração especial:</span><span class="sxs-lookup"><span data-stu-id="471b3-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="471b3-123">Reconstruir índices em tabelas publicadas.</span><span class="sxs-lookup"><span data-stu-id="471b3-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="471b3-124">Adicionar gatilhos de usuário a uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="471b3-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="471b3-125">A ação a seguir exige que você interrompa toda a atividade nas tabelas publicadas:</span><span class="sxs-lookup"><span data-stu-id="471b3-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="471b3-126">Mover uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="471b3-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="471b3-127">As ações a seguir exigem que você descarte a publicação, execute a operação e então recrie a publicação:</span><span class="sxs-lookup"><span data-stu-id="471b3-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="471b3-128">Truncar uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="471b3-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="471b3-129">Renomear uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="471b3-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="471b3-130">Adicionar uma coluna a uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="471b3-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="471b3-131">Descartar ou modificar uma coluna que é publicada para replicação.</span><span class="sxs-lookup"><span data-stu-id="471b3-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="471b3-132">Executar operações não registradas.</span><span class="sxs-lookup"><span data-stu-id="471b3-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="471b3-133">Descartar ou modificar objetos de replicação</span><span class="sxs-lookup"><span data-stu-id="471b3-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="471b3-134">Você deve descartar e reconfigurar o Publicador se descartar ou modificar qualquer tabela de rastreamento de nível, sequência ou procedimento armazenado do Editor.</span><span class="sxs-lookup"><span data-stu-id="471b3-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="471b3-135">Para obter uma lista parcial desses objetos, consulte [Objetos criados no Publicador Oracle](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="471b3-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="471b3-136">Para obter mais informações sobre como descartar e reconfigurar o Publicador, consulte a seção "Alterações que exigem reconfiguração do Publicador" no tópico [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="471b3-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="471b3-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="471b3-137">See Also</span></span>  
 <span data-ttu-id="471b3-138">[Configurar um Publicador Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="471b3-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="471b3-139">[Considerações de design e limitações para Publicadores Oracle](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="471b3-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="471b3-140">Visão geral da publicação do Oracle</span><span class="sxs-lookup"><span data-stu-id="471b3-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
