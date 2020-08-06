---
title: Definir e modificar um filtro de linha parametrizado para um artigo de mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- parameterized filters [SQL Server replication], defining
- parameterized filters [SQL Server replication], modifying
- merge replication [SQL Server replication], dynamic filters
- merge replication parameterized filters [SQL Server replication]
- filters [SQL Server replication], parameterized
- modifying filters, parameterized row
- dynamic filters [SQL Server replication]
ms.assetid: de0482a2-3cc8-4030-8a4a-14364549ac9f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d80ad53661aced22795220507398e2fcc510edd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683465"
---
# <a name="define-and-modify-a-parameterized-row-filter-for-a-merge-article"></a><span data-ttu-id="62c1a-102">Definir e modificar um filtro de linha com parâmetros para um artigo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="62c1a-102">Define and Modify a Parameterized Row Filter for a Merge Article</span></span>
  <span data-ttu-id="62c1a-103">Este tópico descreve como definir e modificar um filtro de linha com parâmetros no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62c1a-103">This topic describes how to define and modify a parameterized row filter in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="62c1a-104">Ao criar artigos de tabela, você pode usar filtros de linha com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="62c1a-104">When creating table articles, you can use parameterized row filters.</span></span> <span data-ttu-id="62c1a-105">Esses filtros usam uma cláusula [WHERE](/sql/t-sql/queries/where-transact-sql) para selecionar os dados apropriados para serem publicados.</span><span class="sxs-lookup"><span data-stu-id="62c1a-105">These filters use a [WHERE](/sql/t-sql/queries/where-transact-sql) clause to select the appropriate data to be published.</span></span> <span data-ttu-id="62c1a-106">Em vez de especificar um valor literal na cláusula (como você faria com um filtro de linha estático), você especifica uma das seguintes funções do sistema ou ambas: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) e [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62c1a-106">Rather than specifying a literal value in the clause (as you do with a static row filter), you specify one or both of the following system functions: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) and [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span></span> <span data-ttu-id="62c1a-107">Para obter mais informações, consulte [Filtros de linha com parâmetros](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-107">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62c1a-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="62c1a-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="62c1a-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="62c1a-109">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="62c1a-110">Se você adicionar, modificar ou excluir um filtro de linha com parâmetros após a inicialização de assinaturas na publicação, será preciso gerar um novo instantâneo e reinicializar todas as assinaturas depois de fazer a alteração.</span><span class="sxs-lookup"><span data-stu-id="62c1a-110">If you add, modify, or delete a parameterized row filter after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="62c1a-111">Para obter mais informações sobre os requisitos para alterações de propriedades, consulte [Alterar propriedades da publicação e do artigo](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-111">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="62c1a-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="62c1a-112">Recommendations</span></span>  
  
-   <span data-ttu-id="62c1a-113">Por motivos de desempenho, recomendamos que não sejam aplicadas funções a nomes de colunas em cláusulas de filtro de linha com parâmetros, como `LEFT([MyColumn]) = SUSER_SNAME()`.</span><span class="sxs-lookup"><span data-stu-id="62c1a-113">For performance reasons, we recommend that you not apply functions to column names in parameterized row filter clauses, such as `LEFT([MyColumn]) = SUSER_SNAME()`.</span></span> <span data-ttu-id="62c1a-114">Se você usar HOST_NAME em uma cláusula de filtro e substituir o valor HOST_NAME, talvez precise converter tipos de dados usando CONVERT.</span><span class="sxs-lookup"><span data-stu-id="62c1a-114">If you use HOST_NAME in a filter clause and override the HOST_NAME value, it might be necessary to convert data types using CONVERT.</span></span> <span data-ttu-id="62c1a-115">Para obter mais informações sobre práticas recomendadas para esse caso, consulte a seção "Substituindo o valor de HOST_NAME()" no tópico [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-115">For more information about best practices for this case, see the section "Overriding the HOST_NAME() Value" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="62c1a-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62c1a-116">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="62c1a-117">Defina, modifique e exclua filtros de linhas com parâmetros na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** da caixa de diálogo **Propriedades da Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="62c1a-117">Define, modify, and delete parameterized row filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="62c1a-118">Para obter mais informações sobre como usar o assistente e acessar a caixa de diálogo, consulte [Criar uma publicação](create-a-publication.md) e [Exibir e modificar as propriedades da publicação](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-118">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter"></a><span data-ttu-id="62c1a-119">Para definir um filtro de linha com parâmetros</span><span class="sxs-lookup"><span data-stu-id="62c1a-119">To define a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="62c1a-120">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades da publicação – \<Publication>** , clique em **Adicionar** e clique em **Adicionar Filtro**.</span><span class="sxs-lookup"><span data-stu-id="62c1a-120">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Add Filter**.</span></span>  
  
2.  <span data-ttu-id="62c1a-121">Na caixa de diálogo **Adicionar Filtro** , selecione uma tabela para filtrar na caixa de listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="62c1a-121">In the **Add Filter** dialog box, select a table to filter from the drop-down list box.</span></span>  
  
3.  <span data-ttu-id="62c1a-122">Crie uma instrução de filtro na caixa de texto **Instrução de filtro** .</span><span class="sxs-lookup"><span data-stu-id="62c1a-122">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="62c1a-123">Você pode digitar diretamente na área de texto e também pode arrastar e soltar colunas da caixa de listagem **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="62c1a-123">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
    -   <span data-ttu-id="62c1a-124">A área de texto **Instrução de filtro** inclui o texto padrão que está no formato de:</span><span class="sxs-lookup"><span data-stu-id="62c1a-124">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
    -   <span data-ttu-id="62c1a-125">O texto padrão não pode ser alterado; digite a cláusula de filtro depois da palavra-chave WHERE usando sintaxe padrão do SQL.</span><span class="sxs-lookup"><span data-stu-id="62c1a-125">The default text cannot be changed; type the filter clause after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="62c1a-126">Um filtro com parâmetros inclui uma chamada para a função de sistema `HOST_NAME()` e/ou `SUSER_SNAME()`, ou uma função definida pelo usuário que referencie uma ou ambas as funções.</span><span class="sxs-lookup"><span data-stu-id="62c1a-126">A parameterized filter includes a call to the system function `HOST_NAME()` and/or `SUSER_SNAME()`, or a user-defined function that references one or both of these functions.</span></span> <span data-ttu-id="62c1a-127">A seguir há um exemplo de uma cláusula de filtro completa para um filtro de linha com parâmetros:</span><span class="sxs-lookup"><span data-stu-id="62c1a-127">The following is an example of a complete filter clause for a parameterized row filter:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="62c1a-128">A cláusula WHERE deve usar nomeação de duas partes; nomeação de três partes e nomeação de quatro partes não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="62c1a-128">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
4.  <span data-ttu-id="62c1a-129">Selecione a opção que corresponde ao modo em que os dados serão compartilhados entre Assinantes:</span><span class="sxs-lookup"><span data-stu-id="62c1a-129">Select the option that matches how data will be shared among Subscribers:</span></span>  
  
    -   <span data-ttu-id="62c1a-130">**Uma linha dessa tabela irá para múltiplas assinaturas**</span><span class="sxs-lookup"><span data-stu-id="62c1a-130">**A row from this table will go to multiple subscriptions**</span></span>  
  
    -   <span data-ttu-id="62c1a-131">**Uma linha dessa tabela irá para apenas uma assinatura**</span><span class="sxs-lookup"><span data-stu-id="62c1a-131">**A row from this table will go to only one subscription**</span></span>  
  
     <span data-ttu-id="62c1a-132">Se você selecionar **Uma linha desta tabela irá para apenas uma assinatura**, a replicação de mesclagem pode otimizar o desempenho armazenando e processando uma quantia menor de metadados.</span><span class="sxs-lookup"><span data-stu-id="62c1a-132">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="62c1a-133">No entanto, será necessário certificar-se de que os dados são particionados de forma que uma linha não seja replicada em mais de um Assinante.</span><span class="sxs-lookup"><span data-stu-id="62c1a-133">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="62c1a-134">Para obter mais informações, consulte a seção "Configurando opções de partição" no tópico [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-134">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="62c1a-135">Se você estiver na caixa de diálogo **Propriedades da Publicação – \<Publication>** , clique em **OK** para salvar e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="62c1a-135">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
#### <a name="to-modify-a-parameterized-row-filter"></a><span data-ttu-id="62c1a-136">Para modificar um filtro de linha com parâmetros</span><span class="sxs-lookup"><span data-stu-id="62c1a-136">To modify a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="62c1a-137">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades da Publicação – \<Publication>** , selecione um filtro no painel **Tabelas Filtradas** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="62c1a-137">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="62c1a-138">Na caixa de diálogo **Editar Filtro** , modifique o filtro.</span><span class="sxs-lookup"><span data-stu-id="62c1a-138">In the **Edit Filter** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-delete-a-parameterized-row-filter"></a><span data-ttu-id="62c1a-139">Para excluir um filtro de linha com parâmetros</span><span class="sxs-lookup"><span data-stu-id="62c1a-139">To delete a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="62c1a-140">Na página **Filtrar Linhas da Tabela** do Assistente para Nova Publicação ou na página **Filtrar Linhas** de **Propriedades da Publicação – \<Publication>** , selecione um filtro no painel **Tabelas Filtradas** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="62c1a-140">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="62c1a-141">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62c1a-141">Using Transact-SQL</span></span>  
 <span data-ttu-id="62c1a-142">Os filtros de linha com parâmetros podem ser criados e modificados de forma programada, usando os procedimentos de replicação armazenados.</span><span class="sxs-lookup"><span data-stu-id="62c1a-142">Parameterized row filters can be created and modified programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="62c1a-143">Para definir um filtro de linha com parâmetros para um artigo em uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="62c1a-143">To define a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="62c1a-144">No Publicador no banco de dados de publicação, execute o [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62c1a-144">At the Publisher on the publication database, execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="62c1a-145">Especifique **@publication** , um nome para o artigo para **@article** , a tabela que está sendo publicada **@source_object** , a cláusula WHERE que define o filtro com parâmetros para **@subset_filterclause** (não incluindo `WHERE` ) e um dos valores a seguir para **@partition_options** , que descreve o tipo de particionamento que resultará do filtro de linha com parâmetros:</span><span class="sxs-lookup"><span data-stu-id="62c1a-145">Specify **@publication**, a name for the article for **@article**, the table being published for **@source_object**, the WHERE clause that defines the parameterized filter for **@subset_filterclause** (not including `WHERE`), and one of the following values for **@partition_options**, which describes the type of partitioning that will result from the parameterized row filter:</span></span>  
  
    -   <span data-ttu-id="62c1a-146">**0** - A filtragem para o artigo ou é estática ou não gera um único subconjunto de dados para cada partição (uma partição “sobreposta”).</span><span class="sxs-lookup"><span data-stu-id="62c1a-146">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="62c1a-147">**1** = As partições resultantes são sobrepostas e as atualizações realizadas no Assinante não podem alterar a partição à qual uma linha pertence.</span><span class="sxs-lookup"><span data-stu-id="62c1a-147">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="62c1a-148">**2** - A filtragem para o artigo gera partições não sobrepostas, mas vários Assinantes podem receber a mesma partição.</span><span class="sxs-lookup"><span data-stu-id="62c1a-148">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="62c1a-149">**3** = A filtragem para o artigo gera partições não sobrepostas que são exclusivas para cada assinatura.</span><span class="sxs-lookup"><span data-stu-id="62c1a-149">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
#### <a name="to-change-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="62c1a-150">Para alterar um filtro de linha com parâmetros para um artigo em uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="62c1a-150">To change a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="62c1a-151">No Publicador do banco de dados de publicação, execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62c1a-151">At the Publisher on the publication database, execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span></span> <span data-ttu-id="62c1a-152">Especifique **@publication** , **@article** , um valor de `subset_filterclause` para **@property** , a expressão que define o filtro com parâmetros para **@value** (não incluindo `WHERE` ) e um valor de **1** para **@force_invalidate_snapshot** e **@force_reinit_subscription** .</span><span class="sxs-lookup"><span data-stu-id="62c1a-152">Specify **@publication**, **@article**, a value of `subset_filterclause` for **@property**, the expression that defines the parameterized filter for **@value** (not including `WHERE`), and a value of **1** for both **@force_invalidate_snapshot** and **@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="62c1a-153">Se esta alteração resultar em um comportamento de particionamento diferente, execute então [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) novamente.</span><span class="sxs-lookup"><span data-stu-id="62c1a-153">If this change results in different partitioning behavior, then execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) again.</span></span> <span data-ttu-id="62c1a-154">Especifique **@publication** , **@article** , um valor de `partition_options` para e **@property** a opção de particionamento mais apropriada para o **@value** , que pode ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="62c1a-154">Specify **@publication**, **@article**, a value of `partition_options` for **@property**, and the most appropriate partitioning option for **@value**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="62c1a-155">**0** - A filtragem para o artigo ou é estática ou não gera um único subconjunto de dados para cada partição (uma partição “sobreposta”).</span><span class="sxs-lookup"><span data-stu-id="62c1a-155">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="62c1a-156">**1** = As partições resultantes são sobrepostas e as atualizações realizadas no Assinante não podem alterar a partição à qual uma linha pertence.</span><span class="sxs-lookup"><span data-stu-id="62c1a-156">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="62c1a-157">**2** - A filtragem para o artigo gera partições não sobrepostas, mas vários Assinantes podem receber a mesma partição.</span><span class="sxs-lookup"><span data-stu-id="62c1a-157">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="62c1a-158">**3** = A filtragem para o artigo gera partições não sobrepostas que são exclusivas para cada assinatura.</span><span class="sxs-lookup"><span data-stu-id="62c1a-158">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="62c1a-159">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="62c1a-159">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="62c1a-160">Esse exemplo define um grupo de artigos em uma publicação de mesclagem onde os artigos são filtrados por uma série de filtros de junção em relação à tabela `Employee` que, por sua vez, é filtrada usando um filtro de linha com parâmetros na coluna **LoginID** .</span><span class="sxs-lookup"><span data-stu-id="62c1a-160">This example defines a group of articles in a merge publication where the articles are filtered with a series of join filters against the `Employee` table that is itself filtered using a parameterized row filter on the **LoginID** column.</span></span> <span data-ttu-id="62c1a-161">Durante a sincronização, o valor retornado pela função [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) é substituído.</span><span class="sxs-lookup"><span data-stu-id="62c1a-161">During synchronization, the value returned by the [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) function is overridden.</span></span> <span data-ttu-id="62c1a-162">Para obter mais informações, consulte Substituindo o valor do HOST_NAME () no tópico [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="62c1a-162">For more information, see Overriding the HOST_NAME() Value in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 [!code-sql[HowTo#sp_MergeDynamicPub1](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepubdynamic1.sql#sp_mergedynamicpub1)]  
  
  
## <a name="see-also"></a><span data-ttu-id="62c1a-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62c1a-163">See Also</span></span>  
 <span data-ttu-id="62c1a-164">[Definir e modificar um filtro de junção entre artigos de mesclagem](define-and-modify-a-join-filter-between-merge-articles.md) </span><span class="sxs-lookup"><span data-stu-id="62c1a-164">[Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md) </span></span>  
 <span data-ttu-id="62c1a-165">[Alterar propriedades da publicação e do artigo](change-publication-and-article-properties.md) </span><span class="sxs-lookup"><span data-stu-id="62c1a-165">[Change Publication and Article Properties](change-publication-and-article-properties.md) </span></span>  
 <span data-ttu-id="62c1a-166">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="62c1a-166">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="62c1a-167">Parameterized Row Filters</span><span class="sxs-lookup"><span data-stu-id="62c1a-167">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
