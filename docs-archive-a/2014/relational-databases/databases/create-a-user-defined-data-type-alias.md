---
title: Criar um alias de tipo de dados definido pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568626"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="65c4a-102">Criar um alias de tipo de dados definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="65c4a-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="65c4a-103">Este tópico descreve como criar um novo alias de tipo de dados definido pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c4a-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="65c4a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="65c4a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65c4a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="65c4a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65c4a-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="65c4a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="65c4a-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="65c4a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65c4a-108">**Para criar um alias de tipo de dados definido pelo usuário, usando:**</span><span class="sxs-lookup"><span data-stu-id="65c4a-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="65c4a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65c4a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="65c4a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65c4a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65c4a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="65c4a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="65c4a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="65c4a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="65c4a-113">O nome de um alias de tipo de dados definido pelo usuário deve estar de acordo com as regras para identificadores.</span><span class="sxs-lookup"><span data-stu-id="65c4a-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65c4a-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="65c4a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65c4a-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="65c4a-115">Permissions</span></span>  
 <span data-ttu-id="65c4a-116">Exige a permissão CREATE TYPE no banco de dados atual e a permissão ALTER no *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="65c4a-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="65c4a-117">Se *schema_name* não for especificado, serão aplicadas as regras de resolução de nome padrão para determinar o esquema do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="65c4a-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="65c4a-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65c4a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="65c4a-119">Para criar um tipo de dados definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="65c4a-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="65c4a-120">No Pesquisador de Objetos, expanda **Bancos de dados**, expanda um banco de dados, expanda **Programação**, expanda **Tipos**, clique com o botão direito do mouse em **Tipos de Dados Definidos pelo Usuário**e clique em **Novo Tipo de Dados Definido pelo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="65c4a-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="65c4a-121">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="65c4a-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="65c4a-122">Especifique se o tipo de dados definido pelo usuário pode aceitar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="65c4a-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="65c4a-123">A nulidade de um tipo de dados definido pelo usuário existente não é editável.</span><span class="sxs-lookup"><span data-stu-id="65c4a-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="65c4a-124">**Data type**</span><span class="sxs-lookup"><span data-stu-id="65c4a-124">**Data type**</span></span>  
     <span data-ttu-id="65c4a-125">Selecione o tipo de dados base na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="65c4a-125">Select the base data type from the list box.</span></span> <span data-ttu-id="65c4a-126">A caixa de listagem exibe todos os tipos de dados, com exceção do tipo de dados `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` e `xml`.</span><span class="sxs-lookup"><span data-stu-id="65c4a-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="65c4a-127">O tipo de dados definido pelo usuário existente não é editável.</span><span class="sxs-lookup"><span data-stu-id="65c4a-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="65c4a-128">**Default**</span><span class="sxs-lookup"><span data-stu-id="65c4a-128">**Default**</span></span>  
     <span data-ttu-id="65c4a-129">Opcionalmente, selecione uma regra ou um padrão para associar ao alias do tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65c4a-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="65c4a-130">**Comprimento/Precisão**</span><span class="sxs-lookup"><span data-stu-id="65c4a-130">**Length/Precision**</span></span>  
     <span data-ttu-id="65c4a-131">Exibe o comprimento ou a precisão do tipo de dados, conforme aplicável.</span><span class="sxs-lookup"><span data-stu-id="65c4a-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="65c4a-132">**Tamanho** se aplica a tipos de dados definidos pelo usuário com base em caracteres; **Precisão** se aplica apenas a tipos de dados definidos pelo usuário com base numérica.</span><span class="sxs-lookup"><span data-stu-id="65c4a-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="65c4a-133">O rótulo se altera dependendo do tipo de dados selecionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="65c4a-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="65c4a-134">Essa caixa não será editável se o comprimento ou a precisão do tipo de dados selecionado for fixo.</span><span class="sxs-lookup"><span data-stu-id="65c4a-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="65c4a-135">Não é exibido comprimento para tipos de dados `nvarchar(max)`, `varchar(max)`ou `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="65c4a-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="65c4a-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="65c4a-136">**Name**</span></span>  
     <span data-ttu-id="65c4a-137">Se você estiver criando um novo alias de tipo de dados definido pelo usuário, digite um nome exclusivo a ser usado no banco de dados para representar o tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65c4a-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="65c4a-138">O número máximo de caracteres deve corresponder ao tipo de dados do sistema `sysname` .</span><span class="sxs-lookup"><span data-stu-id="65c4a-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="65c4a-139">O nome de um alias de tipo de dados definido pelo usuário existente não é editável.</span><span class="sxs-lookup"><span data-stu-id="65c4a-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="65c4a-140">**Regra**</span><span class="sxs-lookup"><span data-stu-id="65c4a-140">**Rule**</span></span>  
     <span data-ttu-id="65c4a-141">Opcionalmente, selecione uma regra para associar ao alias de tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65c4a-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="65c4a-142">**Escala**</span><span class="sxs-lookup"><span data-stu-id="65c4a-142">**Scale**</span></span>  
     <span data-ttu-id="65c4a-143">Especifique o número máximo de dígitos decimais que podem ser armazenados à direita do ponto decimal.</span><span class="sxs-lookup"><span data-stu-id="65c4a-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="65c4a-144">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="65c4a-144">**Schema**</span></span>  
     <span data-ttu-id="65c4a-145">Selecione um esquema de uma lista de todos os esquemas disponíveis para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="65c4a-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="65c4a-146">A seleção padrão é o esquema padrão do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="65c4a-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="65c4a-147">**Storage**</span><span class="sxs-lookup"><span data-stu-id="65c4a-147">**Storage**</span></span>  
     <span data-ttu-id="65c4a-148">Exibe o tamanho de armazenamento máximo para o alias de tipo de dados definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65c4a-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="65c4a-149">Os tamanhos máximos de armazenamento variam com base na precisão.</span><span class="sxs-lookup"><span data-stu-id="65c4a-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="65c4a-150">1 - 9</span><span class="sxs-lookup"><span data-stu-id="65c4a-150">1 - 9</span></span>|<span data-ttu-id="65c4a-151">5</span><span class="sxs-lookup"><span data-stu-id="65c4a-151">5</span></span>|  
    |<span data-ttu-id="65c4a-152">10 – 19</span><span class="sxs-lookup"><span data-stu-id="65c4a-152">10 - 19</span></span>|<span data-ttu-id="65c4a-153">9</span><span class="sxs-lookup"><span data-stu-id="65c4a-153">9</span></span>|  
    |<span data-ttu-id="65c4a-154">20 – 28</span><span class="sxs-lookup"><span data-stu-id="65c4a-154">20 - 28</span></span>|<span data-ttu-id="65c4a-155">13</span><span class="sxs-lookup"><span data-stu-id="65c4a-155">13</span></span>|  
    |<span data-ttu-id="65c4a-156">29 – 38</span><span class="sxs-lookup"><span data-stu-id="65c4a-156">29 - 38</span></span>|<span data-ttu-id="65c4a-157">17</span><span class="sxs-lookup"><span data-stu-id="65c4a-157">17</span></span>|  
  
     <span data-ttu-id="65c4a-158">Para `nchar` os `nvarchar` tipos de dados e, o valor de armazenamento é sempre duas vezes o valor em **comprimento**.</span><span class="sxs-lookup"><span data-stu-id="65c4a-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="65c4a-159">Não é exibido armazenamento para tipos de dados `nvarchar(max)`, `varchar(max)`ou `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="65c4a-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="65c4a-160">Na caixa de diálogo **Tipo de Dados Definido pelo Usuário** , na caixa **Esquema** , digite o esquema próprio para esse alias de tipo de dados ou use o botão Procurar para selecionar o esquema.</span><span class="sxs-lookup"><span data-stu-id="65c4a-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="65c4a-161">Na caixa **Nome** , digite um nome para o novo alias de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="65c4a-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="65c4a-162">Na caixa **Tipo de dados** , selecione o tipo de dados que servirá de base para o novo alias de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="65c4a-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="65c4a-163">Complete as caixas **Tamanho**, **Precisão**e **Escala** caso seja adequado para aquele tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="65c4a-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="65c4a-164">Marque **Permitir NULLs** , se o novo alias de tipo de dados puder permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="65c4a-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="65c4a-165">Na área **Associação** , preencha a caixa **Padrão** ou **Regra** caso queira associar um padrão ou uma regra ao novo alias de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="65c4a-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="65c4a-166">Padrões e regras não podem ser criados no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c4a-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="65c4a-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c4a-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="65c4a-168">Código de exemplo para criação de padrões e regras disponíveis no Explorador de Modelos.</span><span class="sxs-lookup"><span data-stu-id="65c4a-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="65c4a-169">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65c4a-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="65c4a-170">Para criar um alias de tipo de dados definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="65c4a-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="65c4a-171">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c4a-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65c4a-172">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="65c4a-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65c4a-173">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="65c4a-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="65c4a-174">Este exemplo cria um alias de tipo de dados com base no tipo de dados `varchar` fornecido pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="65c4a-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="65c4a-175">O alias de tipo de dados `ssn` é usado para colunas contendo números de previdência social de 11 dígitos (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="65c4a-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="65c4a-176">A coluna não pode ser NULL.</span><span class="sxs-lookup"><span data-stu-id="65c4a-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="65c4a-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65c4a-177">See Also</span></span>  
 <span data-ttu-id="65c4a-178">[Identificadores de banco de dados](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="65c4a-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="65c4a-179">CREATE TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65c4a-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
