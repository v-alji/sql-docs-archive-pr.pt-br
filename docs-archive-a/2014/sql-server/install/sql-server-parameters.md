---
title: Parâmetros de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683305"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="18885-102">Parâmetros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="18885-102">SQL Server Parameters</span></span>
  <span data-ttu-id="18885-103">Nesta página, é possível definir os parâmetros que o analisador usará para análise do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18885-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="18885-104">É possível analisar um, vários ou todos os bancos de dados, analisar arquivos de rastreamento criados usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e analisar arquivos em lote do SQL.</span><span class="sxs-lookup"><span data-stu-id="18885-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18885-105">Alguns problemas de atualização poderão ser detectados somente se você submeter arquivos de rastreamento ou arquivos em lote do SQL à análise.</span><span class="sxs-lookup"><span data-stu-id="18885-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="18885-106">Opções</span><span class="sxs-lookup"><span data-stu-id="18885-106">Options</span></span>  
 <span data-ttu-id="18885-107">**Banco(s) de dados a serem analisados**</span><span class="sxs-lookup"><span data-stu-id="18885-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="18885-108">Para analisar todos os bancos de dados, marque a caixa de seleção **todos os bancos de dados** .</span><span class="sxs-lookup"><span data-stu-id="18885-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="18885-109">Para analisar uma seleção de bancos de dados, marque a caixa de seleção próxima a cada banco de dados para incluir na verificação.</span><span class="sxs-lookup"><span data-stu-id="18885-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="18885-110">**Analisar arquivo(s) de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="18885-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="18885-111">Marque esta caixa de seleção para analisar arquivos de rastreamento no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="18885-112">**Caminho do(s) arquivo(s) de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="18885-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="18885-113">Você pode analisar um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-113">You can analyze one or more files.</span></span> <span data-ttu-id="18885-114">É possível navegar até um local e selecionar vários arquivos ou fornecer vários nomes de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="18885-115">Use o nome do caminho completo para cada arquivo, incluindo o nome do arquivo, e separe as entrada usando o caractere barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="18885-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="18885-116">Se você habilitar **analisar arquivo (s) de rastreamento**, **Avançar** será desabilitado até que você insira um nome de caminho e um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="18885-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="18885-117">**Analisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo (s) em lotes**</span><span class="sxs-lookup"><span data-stu-id="18885-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="18885-118">Marque essa caixa de seleção para analisar arquivos em lote do [!INCLUDE[tsql](../../includes/tsql-md.md)] no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="18885-119">**Caminho para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo (s) em lotes**</span><span class="sxs-lookup"><span data-stu-id="18885-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="18885-120">Você pode analisar um ou mais lotes de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="18885-121">Você pode navegar até um local e selecionar vários arquivos ou pode digitar vários nomes de arquivos.</span><span class="sxs-lookup"><span data-stu-id="18885-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="18885-122">Use o nome do caminho completo para cada arquivo, incluindo o nome do arquivo, e separe as entrada usando o caractere barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="18885-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="18885-123">Se você habilitar **analisar arquivo (s) do lote SQL**, o botão **Avançar** será desabilitado até que você insira um nome de caminho e um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="18885-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="18885-124">**Separador de Lotes do SQL**</span><span class="sxs-lookup"><span data-stu-id="18885-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="18885-125">O texto que é usado para separar lotes de instruções do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18885-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="18885-126">O valor padrão é **go**.</span><span class="sxs-lookup"><span data-stu-id="18885-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18885-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18885-127">See Also</span></span>  
 <span data-ttu-id="18885-128">[Trabalhando com o supervisor de atualização](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="18885-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="18885-129">Referência da interface de usuário do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="18885-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
