---
title: Opção de configuração de servidor default trace enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684894"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="3a485-102">Opção de configuração de servidor default trace enabled</span><span class="sxs-lookup"><span data-stu-id="3a485-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="3a485-103">Use a opção **default trace enabled** para habilitar ou desabilitar os arquivos de log de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="3a485-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="3a485-104">A funcionalidade de rastreamento padrão proporciona um log detalhado e persistente de atividades e alterações relacionadas principalmente às opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="3a485-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="3a485-105">Em vez disso, use Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="3a485-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="3a485-106">Finalidade</span><span class="sxs-lookup"><span data-stu-id="3a485-106">Purpose</span></span>  
 <span data-ttu-id="3a485-107">O rastreamento padrão proporciona assistência à solução de problemas para administradores de banco de dados, garantindo que eles disponham do log dos dados necessários para diagnosticar problemas na primeira vez em que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="3a485-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="3a485-108">Exibindo</span><span class="sxs-lookup"><span data-stu-id="3a485-108">Viewing</span></span>  
 <span data-ttu-id="3a485-109">Os logs de rastreamento padrão podem ser abertos e examinados através do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou consultados com [!INCLUDE[tsql](../../includes/tsql-md.md)] por meio da função do sistema `fn_trace_gettable` .</span><span class="sxs-lookup"><span data-stu-id="3a485-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="3a485-110">abre os arquivos de log de rastreamento padrão da mesma forma que os arquivos de saída de rastreamento normais.</span><span class="sxs-lookup"><span data-stu-id="3a485-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="3a485-111">O log de rastreamento padrão é armazenado, por padrão, no diretório `\MSSQL\LOG` usando um arquivo de rastreamento de substituição.</span><span class="sxs-lookup"><span data-stu-id="3a485-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="3a485-112">O nome de arquivo de base para o arquivo de log de rastreamento padrão é `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="3a485-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="3a485-113">Em uma instalação típica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o rastreamento padrão encontra-se habilitado e, desse modo, torna-se TraceID 1.</span><span class="sxs-lookup"><span data-stu-id="3a485-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="3a485-114">Se habilitado após a instalação e a criação de outros rastreamentos, TraceID pode se tornar um número maior.</span><span class="sxs-lookup"><span data-stu-id="3a485-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="3a485-115">Para obter mais informações sobre como usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler para exibir esse arquivo de rastreamento, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="3a485-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="3a485-116">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a485-116">Example:</span></span>  
 <span data-ttu-id="3a485-117">A instrução a seguir abre o log de rastreamento padrão no local padrão:</span><span class="sxs-lookup"><span data-stu-id="3a485-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="3a485-118">Configurando</span><span class="sxs-lookup"><span data-stu-id="3a485-118">Configuring</span></span>  
 <span data-ttu-id="3a485-119">Quando definida como 1, a opção **default trace enabled** habilita o **Rastreamento Padrão**.</span><span class="sxs-lookup"><span data-stu-id="3a485-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="3a485-120">A configuração padrão desta opção é 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="3a485-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="3a485-121">Um valor 0 desativa o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="3a485-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="3a485-122">A opção **default trace enabled** é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="3a485-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="3a485-123">Se estiver usando o procedimento armazenado do sistema **sp_configure** para alterar a configuração, você só poderá alterar a opção **default trace enabled** quando **show advanced options** estiver definida como 1.</span><span class="sxs-lookup"><span data-stu-id="3a485-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="3a485-124">A configuração entra em vigor imediatamente sem a reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="3a485-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a485-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a485-125">See Also</span></span>  
 <span data-ttu-id="3a485-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a485-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="3a485-127">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a485-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="3a485-128">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3a485-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
