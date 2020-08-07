---
title: Gerar automaticamente um conjunto de filtros de junção entre artigos de mesclagem (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568446"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="c5e98-102">Gerar automaticamente um conjunto de filtros de junção entre artigos de mesclagem (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c5e98-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c5e98-103">Gere automaticamente um conjunto de filtros de junção na página **Filtrar Linhas da Tabela** no Assistente para Nova Publicação ou na página **Filtrar Linhas** da caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="c5e98-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="c5e98-104">Para obter mais informações sobre como usar o assistente e acessar a caixa de diálogo, consulte [Criar uma publicação](create-a-publication.md) e [Exibir e modificar as propriedades da publicação](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c5e98-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5e98-105">Se você gerar automaticamente um conjunto de filtros de junção na caixa de diálogo **Propriedades de Publicação – \<Publication>** após assinaturas a publicação tenham sido inicializadas, será preciso gerar um novo instantâneo e reinicializar todas as assinaturas após fazer a alteração.</span><span class="sxs-lookup"><span data-stu-id="c5e98-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="c5e98-106">Para obter mais informações sobre os requisitos para alterações de propriedades, consulte [Alterar propriedades da publicação e do artigo](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c5e98-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="c5e98-107">Os filtros de junção podem ser criados manualmente para um conjunto de tabelas ou a replicação pode gerar os filtros automaticamente com base em relações de chave estrangeira para chave primária definidas nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="c5e98-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="c5e98-108">Para obter mais informações sobre como criar filtros de junção manualmente, consulte [Definir e modificar um filtro de junção entre artigos de mesclagem](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="c5e98-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="c5e98-109">Para automaticamente gerar um conjunto de filtros de junção entre artigos de mesclagem</span><span class="sxs-lookup"><span data-stu-id="c5e98-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="c5e98-110">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades de Publicação – \<Publication>** , clique em **Adicionar** e clique em **Gerar Filtros Automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="c5e98-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5e98-111">Gerando filtros automaticamente exclui quaisquer filtros de linha ou filtros de junção existentes na publicação.</span><span class="sxs-lookup"><span data-stu-id="c5e98-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="c5e98-112">Você pode adicionar filtros depois de gerar um conjunto de filtros automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c5e98-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="c5e98-113">Siga o processo na caixa de diálogo **Gerar Filtros** para criar um filtro de linha.</span><span class="sxs-lookup"><span data-stu-id="c5e98-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="c5e98-114">O filtro de linha é então estendido para as tabelas relacionadas à tabela filtrada por relações de chave primária e de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="c5e98-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="c5e98-115">Selecione a tabela a ser filtrada a partir da caixa de listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="c5e98-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="c5e98-116">Crie uma instrução de filtro na caixa de texto **Instrução de filtro** .</span><span class="sxs-lookup"><span data-stu-id="c5e98-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="c5e98-117">Você pode digitar diretamente na área de texto e também pode arrastar e soltar colunas da caixa de listagem **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="c5e98-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="c5e98-118">A área de texto **Instrução de filtro** inclui o texto padrão que está no formato de:</span><span class="sxs-lookup"><span data-stu-id="c5e98-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="c5e98-119">O texto padrão não pode ser alterado; digite a cláusula do filtro para um filtro de linha estático ou um filtro de linha com parâmetros após a palavra chave WHERE usando a sintaxe SQL padrão.</span><span class="sxs-lookup"><span data-stu-id="c5e98-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="c5e98-120">A cláusula de filtro completa para um filtro de linha com parâmetros teria este formato:</span><span class="sxs-lookup"><span data-stu-id="c5e98-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="c5e98-121">A cláusula WHERE deve usar nomeação de duas partes; nomeação de três partes e nomeação de quatro partes não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="c5e98-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="c5e98-122">Especifique as opções de filtro.</span><span class="sxs-lookup"><span data-stu-id="c5e98-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="c5e98-123">Selecione a opção que corresponde ao modo em que os dados serão compartilhados entre Assinantes: **Uma linha desta tabela vai para várias assinaturas** ou **Uma linha desta tabela vai para apenas uma assinatura**.</span><span class="sxs-lookup"><span data-stu-id="c5e98-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="c5e98-124">Se você selecionar **Uma linha desta tabela irá para apenas uma assinatura**, a replicação de mesclagem pode otimizar o desempenho armazenando e processando uma quantia menor de metadados.</span><span class="sxs-lookup"><span data-stu-id="c5e98-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="c5e98-125">No entanto, será necessário certificar-se de que os dados são particionados de forma que uma linha não seja replicada em mais de um Assinante.</span><span class="sxs-lookup"><span data-stu-id="c5e98-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="c5e98-126">Para obter mais informações, consulte a seção "Configurando opções de partição" no tópico [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="c5e98-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c5e98-127">O filtro que você especificou é analisado e executado na tabela, na cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="c5e98-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="c5e98-128">Se a instrução de filtro contiver erros de sintaxe ou outros problemas, você será notificado e poderá editar a instrução do filtro.</span><span class="sxs-lookup"><span data-stu-id="c5e98-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="c5e98-129">Depois de a instrução ser analisada, a replicação cria os filtros de junção necessários e os mostra no painel **Tabelas Filtradas** na página **Filtrar Linhas** de **Tabela ou Filtrar Linhas** .</span><span class="sxs-lookup"><span data-stu-id="c5e98-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="c5e98-130">Se você estiver gerando filtros a partir do Assistente para Novas Publicações e ainda não tiver configurado o Distribuidor para o Publicador ao qual o assistente está sendo executado, será solicitado a fazer a configuração.</span><span class="sxs-lookup"><span data-stu-id="c5e98-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="c5e98-131">Se você estiver na caixa de diálogo **Propriedades da Publicação – \<Publication>** , clique em **OK** para salvar e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5e98-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="c5e98-132">Para modificar um filtro que foi gerado automaticamente</span><span class="sxs-lookup"><span data-stu-id="c5e98-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="c5e98-133">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades da Publicação – \<Publication>** , selecione um filtro no painel **Tabelas Filtradas** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c5e98-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="c5e98-134">Na caixa de diálogo do **Editar Filtro** ou **Editar Junção** , modifique o filtro.</span><span class="sxs-lookup"><span data-stu-id="c5e98-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="c5e98-135">Para excluir um filtro que foi gerado automaticamente</span><span class="sxs-lookup"><span data-stu-id="c5e98-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="c5e98-136">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades da Publicação – \<Publication>** , selecione um filtro no painel **Tabelas Filtradas** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c5e98-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e98-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5e98-137">See Also</span></span>  
 <span data-ttu-id="c5e98-138">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="c5e98-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="c5e98-139">Parameterized Row Filters</span><span class="sxs-lookup"><span data-stu-id="c5e98-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
