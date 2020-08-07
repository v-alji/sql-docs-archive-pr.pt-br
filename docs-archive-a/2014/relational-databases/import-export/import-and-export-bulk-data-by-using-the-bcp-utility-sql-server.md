---
title: Importar e exportar dados em massa usando o utilitário bcp (SQL Server) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576382"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="f166d-102">Importar e exportar dados em massa usando o utilitário bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f166d-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="f166d-103">Este tópico oferece uma visão geral de como usar o [utilitário bcp](../../tools/bcp-utility.md) para exportar dados de qualquer lugar para um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , em que uma instrução SELECT atua, incluindo exibições particionadas.</span><span class="sxs-lookup"><span data-stu-id="f166d-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="f166d-104">O utilitário bcp (Bcp.exe) é uma ferramenta de linha de comandos que usa a API do BCP (Programa de cópia em massa).</span><span class="sxs-lookup"><span data-stu-id="f166d-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="f166d-105">O utilitário bcp executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f166d-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="f166d-106">Exporta dados em massa de uma tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="f166d-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="f166d-107">Exporta dados em massa de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="f166d-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="f166d-108">Importa dados em massa de um arquivo de dados para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f166d-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="f166d-109">Gera arquivos de formato.</span><span class="sxs-lookup"><span data-stu-id="f166d-109">Generates format files.</span></span>  
  
 <span data-ttu-id="f166d-110">O utilitário bcp é acessado pelo comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="f166d-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="f166d-111">Caso não esteja usando um arquivo de formato preexistente, para usar o comando **bcp** para importar dados em massa, será necessário compreender o esquema da tabela e os tipos de dados de suas colunas.</span><span class="sxs-lookup"><span data-stu-id="f166d-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="f166d-112">O utilitário bcp pode exportar dados de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados para uso em outros programas.</span><span class="sxs-lookup"><span data-stu-id="f166d-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="f166d-113">O utilitário também pode importar dados de outro programa para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , geralmente outro DBMS (sistema de gerenciamento de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="f166d-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="f166d-114">Os dados são exportados primeiro do programa de origem para um arquivo de dados e, depois, em uma operação separada, copiados do arquivo de dados para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f166d-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="f166d-115">O comando **bcp** oferece opções que você usa para especificar o tipo de dados do arquivo de dados e outras informações.</span><span class="sxs-lookup"><span data-stu-id="f166d-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="f166d-116">Se essas opções não forem especificadas, o comando sugere formatar as informações, como o tipo de campos de dados em um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="f166d-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="f166d-117">O comando pergunta se você quer criar um arquivo de formato que contém suas respostas interativas.</span><span class="sxs-lookup"><span data-stu-id="f166d-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="f166d-118">Se você quiser flexibilidade para operações futuras de importação ou exportação em massa, um arquivo de formato é sempre útil.</span><span class="sxs-lookup"><span data-stu-id="f166d-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="f166d-119">Você pode especificar o arquivo de formato em comandos **bcp** posteriores para arquivos de dados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f166d-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="f166d-120">Para obter mais informações, veja [Especificar formatos de dados para compatibilidade usando bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f166d-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f166d-121">O utilitário bcp é gravado usando a cópia em massa do ODBC</span><span class="sxs-lookup"><span data-stu-id="f166d-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="f166d-122">Para obter uma descrição da sintaxe do comando **bcp** , veja [Utilitário bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f166d-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f166d-123">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f166d-123">Examples</span></span>

 <span data-ttu-id="f166d-124">Para obter exemplos do **bcp**, veja:</span><span class="sxs-lookup"><span data-stu-id="f166d-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="f166d-125">Utilitário bcp</span><span class="sxs-lookup"><span data-stu-id="f166d-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="f166d-126">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="f166d-127">Exemplos de importação e exportação em massa de documentos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="f166d-128">Manter valores de identidade ao importar dados em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="f166d-129">Manter valores nulos ou use os valores padrão durante a importação em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="f166d-130">Especificar terminadores de campo e linha &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="f166d-131">Usar um arquivo de formato para importação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="f166d-132">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="f166d-133">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="f166d-134">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="f166d-135">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f166d-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="f166d-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f166d-136">See Also</span></span>

<span data-ttu-id="f166d-137">[Inserir &#40;&#41;](/sql/t-sql/statements/insert-transact-sql) 
 de Transact-SQL [Cláusula SELECT &#40;&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 Transact-SQL [utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f166d-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="f166d-138">[Preparar para importar &#40;de dados em massa SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md) 
&#41;&#40;Transact [-SQL de BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) 
 [Importação e exportação em massa de &#40;de dados SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="f166d-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>