---
title: Usar SQL Server XEvents (eventos estendidos) para monitorar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576040"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="78dde-102">Usar eventos estendidos do SQL Server (XEvents) para monitorar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="78dde-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="78dde-103">Analysis Services fornece recursos de rastreamento por meio do uso de [eventos estendidos](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="78dde-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="78dde-104">Eventos Estendidos são uma infraestrutura de evento que é altamente escalonável e configurável para sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="78dde-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="78dde-105">Eventos Estendidos são um sistema de monitoramento de desempenho de peso leve que usa poucos recursos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="78dde-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="78dde-106">Todos os eventos de Analysis Services podem ser capturados e direcionados para consumidores específicos, conforme definido em [eventos estendidos](../../relational-databases/extended-events/extended-events.md), por meio de XEvents.</span><span class="sxs-lookup"><span data-stu-id="78dde-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="78dde-107">Iniciando Eventos Estendidos no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="78dde-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="78dde-108">O rastreamento de Eventos Estendidos é habilitado usando um comando de script de objeto de criação XMLA, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="78dde-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="78dde-109">Onde os seguintes elementos serão definidos pelo usuário, dependendo das necessidades do rastreamento:</span><span class="sxs-lookup"><span data-stu-id="78dde-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="78dde-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="78dde-110">*trace_id*</span></span>  
 <span data-ttu-id="78dde-111">Define o identificador exclusivo para este rastreamento.</span><span class="sxs-lookup"><span data-stu-id="78dde-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="78dde-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="78dde-112">*trace_name*</span></span>  
 <span data-ttu-id="78dde-113">O nome especificado para este rastreamento; normalmente uma definição legível do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="78dde-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="78dde-114">O uso do valor *trace_id* como o nome é uma prática comum.</span><span class="sxs-lookup"><span data-stu-id="78dde-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="78dde-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="78dde-115">*AS_event*</span></span>  
 <span data-ttu-id="78dde-116">O evento do Analysis Services a ser exposto.</span><span class="sxs-lookup"><span data-stu-id="78dde-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="78dde-117">Consulte [Eventos de rastreamento do Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) para os nomes dos eventos.</span><span class="sxs-lookup"><span data-stu-id="78dde-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="78dde-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="78dde-118">*data_filename*</span></span>  
 <span data-ttu-id="78dde-119">O nome do arquivo que contém dados dos eventos.</span><span class="sxs-lookup"><span data-stu-id="78dde-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="78dde-120">Este nome terá um carimbo de data/hora como sufixo para evitar a substituição de dados se o rastreamento for enviado repetidas vezes.</span><span class="sxs-lookup"><span data-stu-id="78dde-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="78dde-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="78dde-121">*metadata_filename*</span></span>  
 <span data-ttu-id="78dde-122">O nome do arquivo que contém metadados dos eventos.</span><span class="sxs-lookup"><span data-stu-id="78dde-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="78dde-123">Este nome terá um carimbo de data/hora como sufixo para evitar a substituição de dados se o rastreamento for enviado repetidas vezes.</span><span class="sxs-lookup"><span data-stu-id="78dde-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="78dde-124">Interrompendo eventos estendidos no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="78dde-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="78dde-125">Para interromper o objeto de rastreamento de Eventos Estendidos, exclua esse objeto usando um comando de script de objeto de exclusão XMLA, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="78dde-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="78dde-126">Onde os seguintes elementos serão definidos pelo usuário, dependendo das necessidades do rastreamento:</span><span class="sxs-lookup"><span data-stu-id="78dde-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="78dde-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="78dde-127">*trace_id*</span></span>  
 <span data-ttu-id="78dde-128">Define o identificador exclusivo para o rastreamento a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="78dde-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dde-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="78dde-129">See Also</span></span>  
 [<span data-ttu-id="78dde-130">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="78dde-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
