---
title: Identificadores de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573117"
---
# <a name="database-identifiers"></a><span data-ttu-id="a6e9a-102">Identificadores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a6e9a-102">Database Identifiers</span></span>
  <span data-ttu-id="a6e9a-103">O nome do objeto de banco de dados é conhecido como identificador.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="a6e9a-104">Tudo no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ter um identificador.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="a6e9a-105">Servidores, bancos de dados e objetos de banco de dados, como tabelas, exibições, colunas, índices, gatilhos, procedimentos, restrições e regras, podem ter identificadores.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="a6e9a-106">Os identificadores são necessários para a maioria dos objetos, mas são opcionais para alguns objetos, como restrições.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="a6e9a-107">O identificador de objeto é criado quando o objeto é definido.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="a6e9a-108">O identificador é utilizado para referenciar o objeto.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="a6e9a-109">Por exemplo, a seguinte instrução cria uma tabela com o identificador `TableX`e duas colunas com os identificadores `KeyCol` e `Description`:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="a6e9a-110">Essa tabela também tem uma restrição sem-nome.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="a6e9a-111">A restrição `PRIMARY KEY` não tem identificador.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="a6e9a-112">A ordenação de um identificador depende do nível em que está definido.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="a6e9a-113">Os identificadores de objetos no nível de instância, como logons e nomes de banco de dados, são atribuídos à ordenação padrão da instância.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="a6e9a-114">Os identificadores de objetos em um banco de dados, como tabelas, exibições e nomes de coluna, são atribuídos à ordenação padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="a6e9a-115">Por exemplo, duas tabelas com nomes que se diferem apenas em maiúsculas e minúsculas podem ser criadas em um banco de dados que possui ordenação que diferencia maiúsculas e minúsculas, mas não podem ser criadas em um banco de dados que tem ordenação que não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6e9a-116">Os nomes de variáveis ou os parâmetros de funções e procedimentos armazenados devem obedecer às regras para identificadores [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="a6e9a-117">Classes de identificadores</span><span class="sxs-lookup"><span data-stu-id="a6e9a-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="a6e9a-118">Há duas classes de identificadores:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="a6e9a-119">Identificadores normais</span><span class="sxs-lookup"><span data-stu-id="a6e9a-119">Regular identifiers</span></span>  
 <span data-ttu-id="a6e9a-120">Estão em conformidade com as regras de formato de identificadores.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="a6e9a-121">Os identificadores normais não são delimitados quando utilizados em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="a6e9a-122">Identificadores delimitados</span><span class="sxs-lookup"><span data-stu-id="a6e9a-122">Delimited identifiers</span></span>  
 <span data-ttu-id="a6e9a-123">Estão entre aspas duplas (") ou colchetes ([]).</span><span class="sxs-lookup"><span data-stu-id="a6e9a-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="a6e9a-124">Os identificadores que estão em conformidade com as regras de formato de identificadores podem não ser delimitados.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="a6e9a-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="a6e9a-126">Os identificadores que não estão em conformidade com todas as regras para identificadores devem ser delimitados em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="a6e9a-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="a6e9a-128">Tanto os identificadores normais quanto os delimitados devem conter de 1 a 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="a6e9a-129">Para tabelas temporárias locais, o identificador pode ter no máximo 116 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="a6e9a-130">Regras para identificadores normais</span><span class="sxs-lookup"><span data-stu-id="a6e9a-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="a6e9a-131">Os nomes de variáveis, funções e procedimentos armazenados devem obedecer às regras de identificadores [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="a6e9a-132">O primeiro caractere deve ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="a6e9a-133">Uma letra, como definido pelo Unicode Standard 3.2.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="a6e9a-134">A definição de letras do Unicode inclui caracteres latinos de a até z, de A até Z, além de caracteres de letras de outros idiomas.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="a6e9a-135">Sublinhado (_), arroba (@) ou sinal de número (#).</span><span class="sxs-lookup"><span data-stu-id="a6e9a-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="a6e9a-136">Determinados símbolos no começo de um identificador possuem um significado especial no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6e9a-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6e9a-137">Um identificador normal iniciado com arroba denota sempre uma variável local ou parâmetro e não pode ser utilizado como nome de qualquer outro tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="a6e9a-138">Um identificador iniciado com um sinal de número denota uma tabela temporária ou procedimento.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="a6e9a-139">Um identificador iniciado com dois sinais de número (##) denota um objeto temporário global.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="a6e9a-140">Embora possa ser utilizado um caractere de sinal de número ou dois sinais de número para começar os nomes de outros tipos de objetos, não recomendamos essa prática.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="a6e9a-141">Algumas funções do [!INCLUDE[tsql](../../includes/tsql-md.md)] têm nomes iniciados com dois sinais de arroba (@@).</span><span class="sxs-lookup"><span data-stu-id="a6e9a-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="a6e9a-142">Para evitar confusão com essas funções, você não deverá usar nomes iniciados por @@.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="a6e9a-143">Os caracteres subsequentes podem incluir:</span><span class="sxs-lookup"><span data-stu-id="a6e9a-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="a6e9a-144">Letras, como definido no Unicode Standard 3.2.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="a6e9a-145">Números decimais do latim básico ou outros scripts nacionais.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="a6e9a-146">Arroba (@), cifrão ($), sinal de número (#) ou sublinhado.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="a6e9a-147">O identificador não deve ser uma palavra reservada do [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a6e9a-148">reserva as versões maiúscula e minúscula de palavras reservadas.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="a6e9a-149">Quando identificadores são usados nas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , os identificadores que não estiverem de acordo com essas regras deverão ser delimitados por aspas duplas ou colchetes.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="a6e9a-150">As palavras reservadas dependem do nível de compatibilidade do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="a6e9a-151">Esse nível pode ser definido por meio da instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) .</span><span class="sxs-lookup"><span data-stu-id="a6e9a-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="a6e9a-152">Não são permitidos espaços ou caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="a6e9a-153">Não são permitidos caracteres adicionais.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="a6e9a-154">Quando identificadores são usados nas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , os identificadores que não estiverem de acordo com essas regras deverão ser delimitados por aspas duplas ou colchetes.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6e9a-155">As regras do formato de identificadores normais dependem do nível de compatibilidade do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a6e9a-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="a6e9a-156">Esse nível pode ser definido por meio de [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="a6e9a-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e9a-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6e9a-157">See Also</span></span>  
 <span data-ttu-id="a6e9a-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-169">[Palavras-chave reservadas &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="a6e9a-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6e9a-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="a6e9a-171">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a6e9a-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
