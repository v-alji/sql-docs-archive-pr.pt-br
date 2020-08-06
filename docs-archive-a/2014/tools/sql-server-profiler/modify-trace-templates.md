---
title: Modificar modelos de rastreamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569784"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="b6e66-102">Modificar modelos de rastreamento</span><span class="sxs-lookup"><span data-stu-id="b6e66-102">Modify Trace Templates</span></span>
  <span data-ttu-id="b6e66-103">Você pode modificar os modelos salvos em um arquivo no computador local em que é executado o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e66-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="b6e66-104">Você também pode modificar modelos derivados desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="b6e66-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="b6e66-105">Ao modificar modelos existentes, edite as propriedades do modelo, como classes de evento e colunas de dados, na mesma ordem em que essas propriedades foram definidas originalmente, na guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="b6e66-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="b6e66-106">As classes de evento e colunas de dados podem ser adicionadas ou removidas e os filtros podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="b6e66-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="b6e66-107">Depois que o modelo é modificado, um modelo específico ao usuário é criado, mantendo-se intacto o modelo do sistema original.</span><span class="sxs-lookup"><span data-stu-id="b6e66-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="b6e66-108">Para obter mais informações, veja [Salvar rastreamentos e modelos de rastreamento](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b6e66-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="b6e66-109">Talvez seja necessário derivar um modelo de um arquivo de rastreamento, caso você não consiga se lembrar do modelo original usado para criar o rastreamento (ou não o tenha salvado) ou se desejar executar o mesmo rastreamento em data futura.</span><span class="sxs-lookup"><span data-stu-id="b6e66-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="b6e66-110">Ao trabalhar com rastreamentos existentes, você pode exibir as propriedades, mas não pode modificá-las.</span><span class="sxs-lookup"><span data-stu-id="b6e66-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="b6e66-111">Para modificar as propriedades, interrompa ou pause o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b6e66-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="b6e66-112">Para obter mais informações, veja [Derivar um modelo com base em um arquivo ou uma tabela de rastreamento &#40;SQL Server Profiler&#41;](sql-server-profiler.md) e [Derivar um modelo de um rastreamento em execução &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="b6e66-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="b6e66-113">**Para criar um modelo de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="b6e66-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="b6e66-114">Criar um modelo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="b6e66-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="b6e66-115">**Para executar um rastreamento a partir de um modelo de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="b6e66-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="b6e66-116">Criar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="b6e66-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="b6e66-117">**Para modificar um modelo de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="b6e66-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="b6e66-118">Usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b6e66-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="b6e66-119">Usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6e66-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="b6e66-120">**Para adicionar ou remover eventos de um modelo ou arquivo de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="b6e66-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="b6e66-121">Usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b6e66-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="b6e66-122">Usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6e66-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="b6e66-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6e66-123">See Also</span></span>  
 [<span data-ttu-id="b6e66-124">Iniciar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="b6e66-124">Start a Trace</span></span>](start-a-trace.md)  
  
  
