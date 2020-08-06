---
title: Especificar o fator de preenchimento para um índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684726"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="4f234-102">Especificar fator de preenchimento para um índice</span><span class="sxs-lookup"><span data-stu-id="4f234-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="4f234-103">Este tópico descreve o que é fator de preenchimento e como especificar um valor de fator de preenchimento em um índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f234-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f234-104">A opção fator de preenchimento é fornecida para ajustar o armazenamento e o desempenho de dados de índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="4f234-105">Quando um índice é criado ou recriado, o valor de fator de preenchimento determina a porcentagem de espaço em cada página de nível folha a ser preenchida com dados, reservando o restante em cada página como espaço livre para futuro crescimento.</span><span class="sxs-lookup"><span data-stu-id="4f234-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="4f234-106">Por exemplo, a especificação de um valor de fator de preenchimento de 80 significa que 20 por cento de cada página de nível folha ficará vazio, fornecendo espaço para a expansão do índice à medida que dados forem adicionados à tabela subjacente.</span><span class="sxs-lookup"><span data-stu-id="4f234-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="4f234-107">O espaço vazio é reservado entre as linhas do índice e não no final do índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="4f234-108">O valor de fator de preenchimento é uma porcentagem de 1 a 100 e o padrão para todo o servidor é 0, o que significa que as páginas de nível folha estão totalmente preenchidas.</span><span class="sxs-lookup"><span data-stu-id="4f234-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f234-109">Os valores de fator de preenchimento 0 e 100 são iguais em todos os aspectos.</span><span class="sxs-lookup"><span data-stu-id="4f234-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="4f234-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4f234-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f234-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4f234-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f234-112">Considerações sobre desempenho</span><span class="sxs-lookup"><span data-stu-id="4f234-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="4f234-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="4f234-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f234-114">**Para especificar um fator de preenchimento em um índice usando:**</span><span class="sxs-lookup"><span data-stu-id="4f234-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="4f234-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f234-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f234-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f234-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f234-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4f234-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="4f234-118">Considerações sobre desempenho</span><span class="sxs-lookup"><span data-stu-id="4f234-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="4f234-119">Divisões de página</span><span class="sxs-lookup"><span data-stu-id="4f234-119">Page Splits</span></span>  
 <span data-ttu-id="4f234-120">Um valor de fator de preenchimento corretamente escolhido pode reduzir divisões potenciais de páginas fornecendo espaço suficiente para expansão do índice à medida que são adicionados dados à tabela subjacente. Quando uma nova linha é adicionada a uma página de índice cheia, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] move aproximadamente metade das linhas para uma nova página para fornecer espaço para a nova linha.</span><span class="sxs-lookup"><span data-stu-id="4f234-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="4f234-121">Essa reorganização é conhecida como divisão de página.</span><span class="sxs-lookup"><span data-stu-id="4f234-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="4f234-122">Uma divisão de página abre espaço para novos registros, mas pode demorar a ser executada e é uma operação que consome muitos recursos.</span><span class="sxs-lookup"><span data-stu-id="4f234-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="4f234-123">Além disso, também pode causar fragmentação, o que gera um aumento das operações de E/S.</span><span class="sxs-lookup"><span data-stu-id="4f234-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="4f234-124">Quando ocorrem divisões de página frequentemente, o índice pode ser recriado usando um valor de fator de preenchimento novo ou existente para redistribuir os dados.</span><span class="sxs-lookup"><span data-stu-id="4f234-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="4f234-125">Para obter mais informações, veja [Reorganizar e recriar índices](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4f234-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="4f234-126">Embora um valor de fator de preenchimento baixo, diferente de 0, possa reduzir a necessidade de dividir páginas à medida que o índice cresce, o índice precisará de mais espaço de armazenamento e poderá reduzir o desempenho de leitura.</span><span class="sxs-lookup"><span data-stu-id="4f234-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="4f234-127">Mesmo para um aplicativo orientado para muitas operações de inserção e atualização, o número de leituras de banco de dados normalmente ultrapassa o número de gravações de banco de dados por um fator de 5 a 10.</span><span class="sxs-lookup"><span data-stu-id="4f234-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="4f234-128">Portanto, especificar um fator de preenchimento diferente do padrão pode reduzir o desempenho de leitura de banco de dados em um valor inversamente proporcional à configuração do fator de preenchimento.</span><span class="sxs-lookup"><span data-stu-id="4f234-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="4f234-129">Por exemplo, um valor de fator de preenchimento de 50 pode fazer com que o desempenho de leitura do banco de dados seja reduzido em duas vezes.</span><span class="sxs-lookup"><span data-stu-id="4f234-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="4f234-130">O desempenho de leitura é reduzido porque o índice contém mais páginas, portanto, aumenta as operações de E/S no disco necessárias para recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="4f234-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="4f234-131">Adicionando dados ao final da tabela</span><span class="sxs-lookup"><span data-stu-id="4f234-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="4f234-132">Um fator de preenchimento diferente de zero ou 100 poderá ser bom para o desempenho se os novos dados forem distribuídos uniformemente ao longo da tabela.</span><span class="sxs-lookup"><span data-stu-id="4f234-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="4f234-133">No entanto, se todos os dados forem adicionados ao final da tabela, o espaço vazio nas páginas do índice não será preenchido.</span><span class="sxs-lookup"><span data-stu-id="4f234-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="4f234-134">Por exemplo, se a coluna de chave de índice for uma coluna IDENTITY, a chave de novas linhas estará sempre aumentando e as linhas do índice serão adicionadas logicamente no final do índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="4f234-135">Se as linhas existentes serão atualizadas com dados que aumentam o tamanho das linhas, use um fator de preenchimento menor que 100.</span><span class="sxs-lookup"><span data-stu-id="4f234-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="4f234-136">Os bytes adicionais em cada página ajudarão minimizar divisões de página provocadas pelo comprimento adicional nas linhas.</span><span class="sxs-lookup"><span data-stu-id="4f234-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f234-137">Segurança</span><span class="sxs-lookup"><span data-stu-id="4f234-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f234-138">Permissões</span><span class="sxs-lookup"><span data-stu-id="4f234-138">Permissions</span></span>  
 <span data-ttu-id="4f234-139">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="4f234-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="4f234-140">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="4f234-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f234-141">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f234-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="4f234-142">Para especificar um fator de preenchimento usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="4f234-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="4f234-143">No Pesquisador de Objetos, clique no sinal de adição ao lado do banco de dados que contém a tabela na qual você deseja especificar um fator de preenchimento de índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="4f234-144">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="4f234-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4f234-145">Clique com o botão direito do mouse na tabela para a qual você deseja especificar um fator de preenchimento e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="4f234-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="4f234-146">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="4f234-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="4f234-147">Selecione o índice com o fator de preenchimento que você deseja especificar.</span><span class="sxs-lookup"><span data-stu-id="4f234-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="4f234-148">Expanda **Especificação de Preenchimento**, selecione a linha **Fator de Preenchimento** e digite o fator de preenchimento que você deseja na linha.</span><span class="sxs-lookup"><span data-stu-id="4f234-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="4f234-149">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="4f234-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="4f234-150">No menu **Arquivo** , selecione **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="4f234-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="4f234-151">Para especificar um fator de preenchimento em um índice usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="4f234-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="4f234-152">No Pesquisador de Objetos, clique no sinal de adição ao lado do banco de dados que contém a tabela na qual você deseja especificar um fator de preenchimento de índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="4f234-153">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="4f234-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4f234-154">Clique no sinal de adição para expandir a tabela na qual você deseja especificar um fator de preenchimento de índice.</span><span class="sxs-lookup"><span data-stu-id="4f234-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="4f234-155">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="4f234-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="4f234-156">Clique com o botão direito do mouse no fator de preenchimento a ser especificado e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4f234-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4f234-157">Em **Selecione uma página**, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="4f234-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="4f234-158">Na linha **Fator de Preenchimento** , digite o fator de preenchimento desejado.</span><span class="sxs-lookup"><span data-stu-id="4f234-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="4f234-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f234-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f234-160">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f234-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="4f234-161">Para especificar um fator de preenchimento em um índice existente</span><span class="sxs-lookup"><span data-stu-id="4f234-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="4f234-162">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f234-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f234-163">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f234-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f234-164">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4f234-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f234-165">O exemplo recria um índice existente e aplica o fator de preenchimento especificado durante a operação de reconstrução.</span><span class="sxs-lookup"><span data-stu-id="4f234-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="4f234-166">Outra maneira de especificar um fator de preenchimento em um índice</span><span class="sxs-lookup"><span data-stu-id="4f234-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="4f234-167">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f234-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f234-168">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f234-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f234-169">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4f234-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="4f234-170">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f234-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
