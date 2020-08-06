---
title: Obter informações sobre uma exibição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569267"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="980ca-102">Obter informações sobre uma exibição</span><span class="sxs-lookup"><span data-stu-id="980ca-102">Get Information About a View</span></span>
  <span data-ttu-id="980ca-103">Você pode obter informações sobre a definição ou as propriedades de uma exibição no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="980ca-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="980ca-104">Talvez seja necessário observar a definição da exibição para entender como seus dados são derivados das tabelas de origem, ou consultar os dados definidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="980ca-105">Se você alterar o nome de um objeto referenciado por uma exibição, deverá modificar a exibição, de modo que seu texto reflita o novo nome.</span><span class="sxs-lookup"><span data-stu-id="980ca-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="980ca-106">Portanto, antes de renomear um objeto, exiba primeiramente as dependências do objeto para determinar se as exibições foram afetadas pela mudança proposta.</span><span class="sxs-lookup"><span data-stu-id="980ca-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="980ca-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="980ca-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="980ca-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="980ca-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="980ca-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="980ca-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="980ca-110">**Para obter informações sobre uma exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="980ca-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="980ca-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="980ca-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="980ca-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="980ca-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="980ca-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="980ca-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="980ca-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="980ca-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="980ca-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="980ca-115">Permissions</span></span>  
 <span data-ttu-id="980ca-116">Usar `sp_helptext` para retornar a definição de uma exibição exige associação à função **pública** .</span><span class="sxs-lookup"><span data-stu-id="980ca-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="980ca-117">Usar `sys.sql_expression_dependencies` para localizar todas as dependências em uma exibição exige a permissão VIEW DEFINITION no banco de dados e a permissão SELECT em `sys.sql_expression_dependencies` para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="980ca-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="980ca-118">As definições de objeto de sistema, como as retornadas em SELECT OBJECT_DEFINITION, são publicamente visíveis.</span><span class="sxs-lookup"><span data-stu-id="980ca-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="980ca-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="980ca-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="980ca-120">Obter as propriedades da exibição usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="980ca-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="980ca-121">No **Pesquisador de Objetos**, clique no sinal de adição ao lado do banco de dados que contém a exibição na qual você deseja ver as propriedades e clique no sinal de adição para expandir a pasta **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="980ca-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="980ca-122">Clique com o botão direito do mouse na exibição da qual você deseja ver as propriedades e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="980ca-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="980ca-123">As propriedades a seguir aparecem na caixa de diálogo **Propriedades da Exibição** .</span><span class="sxs-lookup"><span data-stu-id="980ca-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="980ca-124">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="980ca-124">**Database**</span></span>  
     <span data-ttu-id="980ca-125">Nome do banco de dados que contém esta exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="980ca-126">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="980ca-126">**Server**</span></span>  
     <span data-ttu-id="980ca-127">O nome da instância do servidor atual.</span><span class="sxs-lookup"><span data-stu-id="980ca-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="980ca-128">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="980ca-128">**User**</span></span>  
     <span data-ttu-id="980ca-129">Nome do usuário desta conexão.</span><span class="sxs-lookup"><span data-stu-id="980ca-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="980ca-130">**Data da criação**</span><span class="sxs-lookup"><span data-stu-id="980ca-130">**Created date**</span></span>  
     <span data-ttu-id="980ca-131">Exibe a data em que a exibição foi criada.</span><span class="sxs-lookup"><span data-stu-id="980ca-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="980ca-132">**Nome**</span><span class="sxs-lookup"><span data-stu-id="980ca-132">**Name**</span></span>  
     <span data-ttu-id="980ca-133">Nome da exibição atual.</span><span class="sxs-lookup"><span data-stu-id="980ca-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="980ca-134">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="980ca-134">**Schema**</span></span>  
     <span data-ttu-id="980ca-135">Exibe o esquema que possui a exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="980ca-136">**Objeto do sistema**</span><span class="sxs-lookup"><span data-stu-id="980ca-136">**System object**</span></span>  
     <span data-ttu-id="980ca-137">Indica se a exibição é um objeto do sistema.</span><span class="sxs-lookup"><span data-stu-id="980ca-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="980ca-138">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="980ca-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="980ca-139">**ANSI NULLs**</span><span class="sxs-lookup"><span data-stu-id="980ca-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="980ca-140">Indica se o objeto foi criado com a opção ANSI NULLs.</span><span class="sxs-lookup"><span data-stu-id="980ca-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="980ca-141">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="980ca-141">**Encrypted**</span></span>  
     <span data-ttu-id="980ca-142">Indica se a exibição é criptografada.</span><span class="sxs-lookup"><span data-stu-id="980ca-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="980ca-143">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="980ca-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="980ca-144">**Identificador entre aspas**</span><span class="sxs-lookup"><span data-stu-id="980ca-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="980ca-145">Indica se o objeto foi criado com a opção de identificador entre aspas.</span><span class="sxs-lookup"><span data-stu-id="980ca-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="980ca-146">**Ligado a esquema**</span><span class="sxs-lookup"><span data-stu-id="980ca-146">**Schema bound**</span></span>  
     <span data-ttu-id="980ca-147">Indica se a exibição é ligada ao esquema.</span><span class="sxs-lookup"><span data-stu-id="980ca-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="980ca-148">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="980ca-148">Values are True and False.</span></span> <span data-ttu-id="980ca-149">Para obter informações sobre exibições ligadas ao esquema, consulte a parte SCHEMABINDING de [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="980ca-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="980ca-150">Obtendo as propriedades da exibição usando a ferramenta Designer de Exibição</span><span class="sxs-lookup"><span data-stu-id="980ca-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="980ca-151">No **Pesquisador de Objetos**, expanda o banco de dados que contém a exibição da qual você ver as propriedades e expanda a pasta **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="980ca-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="980ca-152">Clique com o botão direito do mouse na exibição da qual você deseja ver as propriedades e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="980ca-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="980ca-153">Clique com o botão direito do mouse no espaço em branco no painel Diagrama e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="980ca-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="980ca-154">As propriedades a seguir aparecem no painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="980ca-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="980ca-155">**(Nome)**</span><span class="sxs-lookup"><span data-stu-id="980ca-155">**(Name)**</span></span>  
     <span data-ttu-id="980ca-156">Nome da exibição atual.</span><span class="sxs-lookup"><span data-stu-id="980ca-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="980ca-157">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="980ca-157">**Database Name**</span></span>  
     <span data-ttu-id="980ca-158">Nome do banco de dados que contém esta exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="980ca-159">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="980ca-159">**Description**</span></span>  
     <span data-ttu-id="980ca-160">Uma breve descrição da exibição atual.</span><span class="sxs-lookup"><span data-stu-id="980ca-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="980ca-161">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="980ca-161">**Schema**</span></span>  
     <span data-ttu-id="980ca-162">Exibe o esquema que possui a exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="980ca-163">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="980ca-163">**Server Name**</span></span>  
     <span data-ttu-id="980ca-164">O nome da instância do servidor atual.</span><span class="sxs-lookup"><span data-stu-id="980ca-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="980ca-165">**Associar a Esquema**</span><span class="sxs-lookup"><span data-stu-id="980ca-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="980ca-166">Impede os usuários de modificar os objetos subjacentes que contribuem com essa exibição de qualquer forma que invalide a definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="980ca-167">**Determinística**</span><span class="sxs-lookup"><span data-stu-id="980ca-167">**Deterministic**</span></span>  
     <span data-ttu-id="980ca-168">Mostra se o tipo de dados da coluna selecionada pode ser determinado com certeza.</span><span class="sxs-lookup"><span data-stu-id="980ca-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="980ca-169">**Valores distintos**</span><span class="sxs-lookup"><span data-stu-id="980ca-169">**Distinct Values**</span></span>  
     <span data-ttu-id="980ca-170">Especifica se a consulta filtrará duplicatas na exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="980ca-171">Essa opção é útil quando você estiver usando apenas algumas das colunas de uma tabela e essas colunas podem conter valores duplicados ou, quando o processo de junção de duas ou mais tabelas produz linhas duplicadas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="980ca-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="980ca-172">Escolher essa opção equivale a inserir a palavra-chave DISTINCT na instrução no painel do SQL.</span><span class="sxs-lookup"><span data-stu-id="980ca-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="980ca-173">**Extensão GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="980ca-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="980ca-174">Especifica de as opções adicionais de exibições com base em consultas de agregação estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="980ca-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="980ca-175">**Todas as Colunas de Saída**</span><span class="sxs-lookup"><span data-stu-id="980ca-175">**Output All Columns**</span></span>  
     <span data-ttu-id="980ca-176">Mostra se todas as colunas são retornadas pela exibição selecionada.</span><span class="sxs-lookup"><span data-stu-id="980ca-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="980ca-177">Isso é definido no momento em que a exibição é criada.</span><span class="sxs-lookup"><span data-stu-id="980ca-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="980ca-178">**Comentário SQL**</span><span class="sxs-lookup"><span data-stu-id="980ca-178">**SQL Comment**</span></span>  
     <span data-ttu-id="980ca-179">Mostra uma descrição das instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="980ca-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="980ca-180">Para ver a descrição inteira ou editá-la, clique nela e, em seguida, clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="980ca-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="980ca-181">Os comentários podem incluir informações como quem usa a exibição e quando ela é usada.</span><span class="sxs-lookup"><span data-stu-id="980ca-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="980ca-182">**Especificação de Top**</span><span class="sxs-lookup"><span data-stu-id="980ca-182">**Top Specification**</span></span>  
     <span data-ttu-id="980ca-183">Expande para mostrar as propriedades **Top**, **Expression**, **Percent**e **With Ties** .</span><span class="sxs-lookup"><span data-stu-id="980ca-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="980ca-184">**(Top)**</span><span class="sxs-lookup"><span data-stu-id="980ca-184">**(Top)**</span></span>  
     <span data-ttu-id="980ca-185">Especifica se a exibição incluirá uma cláusula TOP, que retorna apenas as primeiras linhas n ou primeiro percentual n de linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="980ca-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="980ca-186">O padrão é que a exibição retorne as primeiras 10 linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="980ca-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="980ca-187">Use para alterar o número de linhas para retornar ou especificar uma porcentagem diferente.</span><span class="sxs-lookup"><span data-stu-id="980ca-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="980ca-188">**Expression**</span><span class="sxs-lookup"><span data-stu-id="980ca-188">**Expression**</span></span>  
     <span data-ttu-id="980ca-189">Mostra que porcentagem (se **Percent** for definida como **Sim**) ou registros (se **Percent** for definida como **Não**) a exibição retornará.</span><span class="sxs-lookup"><span data-stu-id="980ca-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="980ca-190">**Percent**</span><span class="sxs-lookup"><span data-stu-id="980ca-190">**Percent**</span></span>  
     <span data-ttu-id="980ca-191">Especifica se a consulta incluirá uma cláusula **TOP** , que retorna apenas o primeiro n percentual de linhas no conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="980ca-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="980ca-192">**With Ties**</span><span class="sxs-lookup"><span data-stu-id="980ca-192">**With Ties**</span></span>  
     <span data-ttu-id="980ca-193">Especifica se a exibição incluirá uma cláusula **WITH TIES** .</span><span class="sxs-lookup"><span data-stu-id="980ca-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="980ca-194">**WITH TIES** é útil se uma exibição incluir uma cláusula **ORDER BY** e uma cláusula **TOP** com base na porcentagem.</span><span class="sxs-lookup"><span data-stu-id="980ca-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="980ca-195">Se essa opção for determinada, e se a porcentagem de corte se encontrar no meio de um conjunto de linhas com valores idênticos na cláusula **ORDER BY** , a exibição será estendida para incluir todas essas linhas.</span><span class="sxs-lookup"><span data-stu-id="980ca-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="980ca-196">**Especificação de atualização**</span><span class="sxs-lookup"><span data-stu-id="980ca-196">**Update Specification**</span></span>  
     <span data-ttu-id="980ca-197">Expande para mostrar as propriedades de **Atualizar Usando Regras de Exibição** e **Verificar Opção** .</span><span class="sxs-lookup"><span data-stu-id="980ca-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="980ca-198">**(Atualizar Usando Regras de Exibição)**</span><span class="sxs-lookup"><span data-stu-id="980ca-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="980ca-199">Indica que todas as atualizações e inserções da exibição serão convertidas pelo MDAC (Microsoft Data Access Components) em instruções SQL que fazem referência à exibição, e não em instruções SQL que fazem referência diretamente às tabelas base da exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="980ca-200">Em alguns casos, o MDAC manifesta as operações de atualização de exibição e inserção de exibição como atualizações e inserções de acordo com as tabelas base subjacentes da exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="980ca-201">Selecionando **Atualizar Usando Regras de Exibição**, você pode assegurar que o MDAC gere operações de atualização e inserção na própria exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="980ca-202">**Verificar Opção**</span><span class="sxs-lookup"><span data-stu-id="980ca-202">**Check Option**</span></span>  
     <span data-ttu-id="980ca-203">Indica que quando você abrir essa exibição e modificar o painel **Resultados** , a fonte de dados verificará se os dados adicionados ou modificados estão de acordo com a cláusula **WHERE** da definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="980ca-204">Se sua modificação não estiver de acordo com a cláusula **WHERE** , você verá um erro com mais informações.</span><span class="sxs-lookup"><span data-stu-id="980ca-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="980ca-205">Para obter as dependências da exibição</span><span class="sxs-lookup"><span data-stu-id="980ca-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="980ca-206">No **Pesquisador de Objetos**, expanda o banco de dados que contém a exibição da qual você ver as propriedades e expanda a pasta **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="980ca-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="980ca-207">Clique com o botão direito do mouse na exibição da qual você deseja ver as propriedades e selecione **Dependências da Exibição**.</span><span class="sxs-lookup"><span data-stu-id="980ca-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="980ca-208">Selecione **Objetos que dependem de [nome da exibição]** para ver os objetos que fazem referência à exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="980ca-209">Selecione **Objetos dos quais [nome da exibição] depende** para ver os objetos que são referenciados pela exibição.</span><span class="sxs-lookup"><span data-stu-id="980ca-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="980ca-210">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="980ca-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="980ca-211">Para obter a definição e as propriedades de uma exibição</span><span class="sxs-lookup"><span data-stu-id="980ca-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="980ca-212">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="980ca-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="980ca-213">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="980ca-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="980ca-214">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="980ca-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="980ca-215">Para obter mais informações, veja [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) e [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="980ca-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="980ca-216">Para obter as dependências de uma exibição</span><span class="sxs-lookup"><span data-stu-id="980ca-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="980ca-217">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="980ca-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="980ca-218">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="980ca-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="980ca-219">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="980ca-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="980ca-220">Para obter mais informações, veja [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="980ca-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
