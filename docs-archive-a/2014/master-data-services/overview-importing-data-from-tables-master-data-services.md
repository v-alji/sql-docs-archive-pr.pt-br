---
title: Importação de dados (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569557"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="f2e5d-102">Importação de dados (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f2e5d-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="f2e5d-103">Depois de criar um modelo para seus dados no [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode começar a adicionar dados e fazer alterações nos dados, no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2e5d-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="f2e5d-104">Você usa as tabelas de preparo do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , procedimentos armazenados e o Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="f2e5d-105">Você também pode usar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] , para adicionar dados ao repositório do MDS ( [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] banco de dado).</span><span class="sxs-lookup"><span data-stu-id="f2e5d-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="f2e5d-106">Para obter mais informações, consulte [Publishing Data &#40;Suplemento MDS para Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f2e5d-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="f2e5d-107">Ao adicionar e atualizar dados, você pode realizar os procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="f2e5d-108">Carregar e atualizar membros e atualizar valores de atributo</span><span class="sxs-lookup"><span data-stu-id="f2e5d-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="f2e5d-109">Desativar e excluir membros</span><span class="sxs-lookup"><span data-stu-id="f2e5d-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="f2e5d-110">Mover membros de hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="f2e5d-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="f2e5d-111">A adição e atualização de dados incluem as principais tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="f2e5d-112">Carregar dados nas tabelas de preparo no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2e5d-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="f2e5d-113">Carregar dados das tabelas de preparo para as tabelas apropriadas do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2e5d-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="f2e5d-114">Use os procedimentos armazenados de preparo ou o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para carregar os dados.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="f2e5d-115">No [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], o suporte para os processos de preparo do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] foi preterido.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="f2e5d-116">Desativando e excluindo membros</span><span class="sxs-lookup"><span data-stu-id="f2e5d-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="f2e5d-117">Desativar significa que o membro pode ser reativado.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="f2e5d-118">Se você reativar um membro, seus atributos e sua associação em hierarquias e coleções serão restaurados.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="f2e5d-119">Todas as transações anteriores estão intactas.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-119">All previous transactions are intact.</span></span> <span data-ttu-id="f2e5d-120">Transações de desativação são visíveis para administradores na área funcional **Gerenciamento de versões** do Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="f2e5d-121">Excluir significa limpar o membro permanentemente do sistema.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="f2e5d-122">Todas as transações do membro, todas as relações e todos os atributos são excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="f2e5d-123">Você não pode usar preparo para reativar membros.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="f2e5d-124">Você deve fazer isto manualmente no Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="f2e5d-125">Para obter mais informações, consulte [Reativar um membro ou uma coleção &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2e5d-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="f2e5d-126">Você não pode usar preparação para excluir ou desativar coleções.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="f2e5d-127">Para obter mais informações sobre como desativar coleções manualmente, consulte [Excluir um membro ou uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2e5d-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="f2e5d-128">Movendo membros de hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="f2e5d-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="f2e5d-129">Quando você move o local dos membros em hierarquias explícitas em massa, você pode designar o seguinte.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="f2e5d-130">Um membro consolidado como um pai de um membro consolidado.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="f2e5d-131">Um membro consolidado como um pai de um membro folha.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="f2e5d-132">Um membro folha como irmão de um membro folha ou consolidado.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="f2e5d-133">Um membro consolidado como irmão de um membro folha ou consolidado.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="f2e5d-134">Tabelas de preparo e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="f2e5d-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="f2e5d-135">O banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] inclui os seguintes tipos de tabelas de preparo que você pode preencher com seus dados.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="f2e5d-136">Tabela de preparo de membros folha &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e5d-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="f2e5d-137">Tabela de preparo de membros consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e5d-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="f2e5d-138">Tabela de preparo de relações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e5d-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="f2e5d-139">Para cada entidade no modelo, existe uma tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="f2e5d-140">O nome da tabela indica a entidade correspondente e o tipo de entidade como membro folha.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="f2e5d-141">A imagem a seguir mostra as tabelas de preparo para as entidades de moeda, cliente e produto.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="f2e5d-142">![Tabelas de preparo no banco de dados do MDS](../../2014/master-data-services/media/mds-stagingtables.png "Tabelas de preparo no banco de dados do MDS")</span><span class="sxs-lookup"><span data-stu-id="f2e5d-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="f2e5d-143">O nome de cada tabela é especificado quando uma entidade é criada e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="f2e5d-144">Se o nome da tabela de preparo contiver um _1 ou outro número, isso significa que outra tabela daquele nome já existia quando a entidade foi criada.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="f2e5d-145">O [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] inclui os seguintes tipos de procedimentos de preparo armazenados.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="f2e5d-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="f2e5d-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="f2e5d-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="f2e5d-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="f2e5d-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="f2e5d-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="f2e5d-149">Para cada entidade no modelo, há três procedimentos armazenados que correspondem ao membro folha, membros consolidados e tabelas de preparo de relação.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="f2e5d-150">A imagem a seguir mostra as tabelas de procedimentos de preparo armazenado para as entidades de moeda, cliente e produto.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="f2e5d-151">![Preparando procedimentos armazenados no banco de dados do MDS](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Preparando procedimentos armazenados no banco de dados do MDS")</span><span class="sxs-lookup"><span data-stu-id="f2e5d-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="f2e5d-152">Para obter mais informações sobre os procedimentos armazenados, consulte [Preparando um procedimento armazenado &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2e5d-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="f2e5d-153">Registrando transações em log</span><span class="sxs-lookup"><span data-stu-id="f2e5d-153">Logging Transactions</span></span>
 <span data-ttu-id="f2e5d-154">Todas as transações que ocorrem quando dados ou relações são importados ou atualizados podem ser registradas em log.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="f2e5d-155">Uma opção do procedimento armazenado permite esse registro em log.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="f2e5d-156">Se você iniciar o processo de preparo usando [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], não ocorrerá registro em log.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="f2e5d-157">No [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], a configuração **Registrar em log as transações de preparo** não se aplica a esse método de dados de preparo.</span><span class="sxs-lookup"><span data-stu-id="f2e5d-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="f2e5d-158">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f2e5d-158">Related Content</span></span>

-   [<span data-ttu-id="f2e5d-159">Validação &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e5d-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="f2e5d-160">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e5d-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)


