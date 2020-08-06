---
title: Verificar subsistema de entrada e saída de disco quanto a problemas de atraso de E/S | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680378"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="34b66-102">Verificar o subsistema de entrada e saída de disco para problemas de atraso de E/S</span><span class="sxs-lookup"><span data-stu-id="34b66-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="34b66-103">Esta regra verifica o log de eventos quanto à mensagem de erro 833.</span><span class="sxs-lookup"><span data-stu-id="34b66-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="34b66-104">Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emitiu uma solicitação de leitura ou gravação de disco, e que a solicitação demorou mais de 15 segundos para retornar.</span><span class="sxs-lookup"><span data-stu-id="34b66-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="34b66-105">Esse erro é informado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica um problema com o subsistema de E/S do disco.</span><span class="sxs-lookup"><span data-stu-id="34b66-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="34b66-106">Atrasos longos podem danificar seriamente o desempenho do ambiente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34b66-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="34b66-107">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="34b66-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="34b66-108">Solucione este erro procurando mensagens de erros relacionados a hardware no log de eventos de sistema.</span><span class="sxs-lookup"><span data-stu-id="34b66-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="34b66-109">Examine também os logs específicos do hardware, se estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="34b66-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="34b66-110">Use o Monitor de Desempenho para examinar os seguintes contadores:</span><span class="sxs-lookup"><span data-stu-id="34b66-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="34b66-111">Transferência média do disco por segundo</span><span class="sxs-lookup"><span data-stu-id="34b66-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="34b66-112">Comprimento médio da fila de disco</span><span class="sxs-lookup"><span data-stu-id="34b66-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="34b66-113">Comprimento da fila atual de disco</span><span class="sxs-lookup"><span data-stu-id="34b66-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="34b66-114">Por exemplo, o tempo médio de Disco seg/Transferência em um computador executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalmente é inferior a 15 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="34b66-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="34b66-115">Se o valor médio de Disco seg/Transferência aumentar, isso indica que o subsistema de E/S do disco não está acompanhando da melhor maneira possível o ritmo da demanda de E/S.</span><span class="sxs-lookup"><span data-stu-id="34b66-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="34b66-116">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="34b66-116">For More Information</span></span>  
 [<span data-ttu-id="34b66-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="34b66-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="34b66-118">Artigo 897284 da Base de Dados de Conhecimento Microsoft</span><span class="sxs-lookup"><span data-stu-id="34b66-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="34b66-119">[Fundamentos de E/S do SQL Server, Capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="34b66-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
