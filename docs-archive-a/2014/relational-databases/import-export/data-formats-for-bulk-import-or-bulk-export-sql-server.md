---
title: Formatos de dados para importar ou exportar em massa (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568563"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="db692-102">Formatos de dados para importar ou exportar em massa (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="db692-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="db692-103">pode aceitar dados em formato de dados de caractere ou formato de dados binário nativos.</span><span class="sxs-lookup"><span data-stu-id="db692-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="db692-104">Use o formato de caractere ao mover dados entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e outro aplicativo (como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) ou outro servidor de banco de dados (como Oracle ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="db692-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="db692-105">O formato nativo só pode ser usado para transferir dados entre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db692-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="db692-106">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="db692-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="db692-107">Formatos de dados para importar ou exportar em massa</span><span class="sxs-lookup"><span data-stu-id="db692-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="db692-108">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="db692-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="db692-109">Formatos de dados para importar ou exportar em massa</span><span class="sxs-lookup"><span data-stu-id="db692-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="db692-110">A tabela a seguir indica o formato de dados que costuma ser adequado ao uso, dependendo de como os dados estão representados e da origem ou destino da operação.</span><span class="sxs-lookup"><span data-stu-id="db692-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="db692-111">Operação</span><span class="sxs-lookup"><span data-stu-id="db692-111">Operation</span></span>|<span data-ttu-id="db692-112">Nativo</span><span class="sxs-lookup"><span data-stu-id="db692-112">Native</span></span>|<span data-ttu-id="db692-113">Unicode nativo</span><span class="sxs-lookup"><span data-stu-id="db692-113">Unicode native</span></span>|<span data-ttu-id="db692-114">Caractere</span><span class="sxs-lookup"><span data-stu-id="db692-114">Character</span></span>|<span data-ttu-id="db692-115">Caractere unicode</span><span class="sxs-lookup"><span data-stu-id="db692-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="db692-116">Transferências de dados em massa entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados que não contém nenhum caractere estendido ou DBCS (conjunto de caracteres de dois bytes).</span><span class="sxs-lookup"><span data-stu-id="db692-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="db692-117">A menos que um arquivo de formato seja usado, essas tabelas devem ser definidas identicamente.</span><span class="sxs-lookup"><span data-stu-id="db692-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="db692-118">Sim<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="db692-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="db692-119">Para colunas `sql_variant`, recomenda-se usar o formato de dados nativos que, ao contrário dos formatos unicode e de caractere, preservam o metadados para cada valor `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="db692-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="db692-120">Sim</span><span class="sxs-lookup"><span data-stu-id="db692-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="db692-121">Transferências de dados em massa entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados que contém caracteres estendidos ou DBCS.</span><span class="sxs-lookup"><span data-stu-id="db692-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="db692-122">Sim</span><span class="sxs-lookup"><span data-stu-id="db692-122">Yes</span></span>|-|-|  
|<span data-ttu-id="db692-123">Importação de dados em massa de um arquivo de texto gerado por outro programa.</span><span class="sxs-lookup"><span data-stu-id="db692-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="db692-124">Sim</span><span class="sxs-lookup"><span data-stu-id="db692-124">Yes</span></span>|-|  
|<span data-ttu-id="db692-125">Exportação de dados em massa para um arquivo de texto que será usado em outro programa.</span><span class="sxs-lookup"><span data-stu-id="db692-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="db692-126">Sim</span><span class="sxs-lookup"><span data-stu-id="db692-126">Yes</span></span>|-|  
|<span data-ttu-id="db692-127">Transferências de dados em massa entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados que contém dados unicode e não contém nenhum caractere estendido ou DBCS.</span><span class="sxs-lookup"><span data-stu-id="db692-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="db692-128">Sim</span><span class="sxs-lookup"><span data-stu-id="db692-128">Yes</span></span>|  
  
 <span data-ttu-id="db692-129"><sup>1</sup> método mais rápido para a exportação de dados em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao usar o **bcp**.</span><span class="sxs-lookup"><span data-stu-id="db692-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="db692-130">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="db692-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="db692-131">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db692-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="db692-132">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db692-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="db692-133">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db692-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="db692-134">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db692-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="db692-135">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="db692-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="db692-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db692-136">See Also</span></span>  
 <span data-ttu-id="db692-137">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db692-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="db692-138">Especificar formatos de dados para compatibilidade usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db692-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
