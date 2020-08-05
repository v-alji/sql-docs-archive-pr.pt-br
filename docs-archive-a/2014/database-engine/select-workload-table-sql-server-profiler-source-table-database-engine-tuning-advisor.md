---
title: SQL Server Profiler-tabela de origem-Orientador de Otimização do Mecanismo de Banco de Dados-selecionar tabela de carga de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572670"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="60b20-102">SQL Server Profiler-tabela de origem-Orientador de Otimização do Mecanismo de Banco de Dados-selecionar tabela de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="60b20-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="60b20-103">O Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] e o Orientador de Otimização do [!INCLUDE[ssDE](../includes/ssde-md.md)] usam essa caixa de diálogo para selecionar tabelas.</span><span class="sxs-lookup"><span data-stu-id="60b20-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="60b20-104">No [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a caixa de diálogo **Tabela de Origem** para especificar uma tabela de origem para uma tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60b20-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="60b20-105">Essa é uma tabela a partir da qual é carregado um rastreamento e cujo conteúdo é exibido ou usado para repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60b20-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="60b20-106">No Orientador de Otimização do [!INCLUDE[ssDE](../includes/ssde-md.md)], use a caixa de diálogo **Selecionar Tabela de Carga de Trabalho** para selecionar uma tabela de banco de dados que contém informações de rastreamento do [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para usar como uma carga de trabalho de otimização ou para visualizar o conteúdo da tabela antes de iniciar a análise de otimização.</span><span class="sxs-lookup"><span data-stu-id="60b20-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="60b20-107">Opções</span><span class="sxs-lookup"><span data-stu-id="60b20-107">Options</span></span>  
 <span data-ttu-id="60b20-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="60b20-108">**SQL Server**</span></span>  
 <span data-ttu-id="60b20-109">Especifica a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] conectada atualmente.</span><span class="sxs-lookup"><span data-stu-id="60b20-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="60b20-110">Esse campo é populado automaticamente e não pode ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="60b20-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="60b20-111">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="60b20-111">**Database**</span></span>  
 <span data-ttu-id="60b20-112">Especifique o banco de dados onde está localizada a tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60b20-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="60b20-113">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="60b20-113">**Owner**</span></span>  
 <span data-ttu-id="60b20-114">Specifies the owner of the trace table.</span><span class="sxs-lookup"><span data-stu-id="60b20-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="60b20-115">Este campo é populado automaticamente como **dbo**.</span><span class="sxs-lookup"><span data-stu-id="60b20-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="60b20-116">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="60b20-116">**Table**</span></span>  
 <span data-ttu-id="60b20-117">Especifique o nome da tabela de rastreamento a partir da qual deve ser lido o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60b20-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b20-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b20-118">See Also</span></span>  
 <span data-ttu-id="60b20-119">[Salvar resultados de rastreamento em uma tabela &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="60b20-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="60b20-120">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="60b20-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="60b20-121">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="60b20-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
