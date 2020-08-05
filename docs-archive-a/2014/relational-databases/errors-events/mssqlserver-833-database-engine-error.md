---
title: MSSQLSERVER_833 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e20018c0fe1cd0748f4930e0022622adcbfad10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573990"
---
# <a name="mssqlserver_833"></a><span data-ttu-id="bdc0c-102">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="bdc0c-102">MSSQLSERVER_833</span></span>
    
## <a name="details"></a><span data-ttu-id="bdc0c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bdc0c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdc0c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bdc0c-104">Product Name</span></span>|<span data-ttu-id="bdc0c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bdc0c-105">SQL Server</span></span>|  
|<span data-ttu-id="bdc0c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bdc0c-106">Event ID</span></span>|<span data-ttu-id="bdc0c-107">833</span><span class="sxs-lookup"><span data-stu-id="bdc0c-107">833</span></span>|  
|<span data-ttu-id="bdc0c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bdc0c-108">Event Source</span></span>|<span data-ttu-id="bdc0c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bdc0c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bdc0c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bdc0c-110">Component</span></span>|<span data-ttu-id="bdc0c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bdc0c-111">SQLEngine</span></span>|  
|<span data-ttu-id="bdc0c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bdc0c-112">Symbolic Name</span></span>|<span data-ttu-id="bdc0c-113">BUF_LONG_IO</span><span class="sxs-lookup"><span data-stu-id="bdc0c-113">BUF_LONG_IO</span></span>|  
|<span data-ttu-id="bdc0c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bdc0c-114">Message Text</span></span>|<span data-ttu-id="bdc0c-115">SQL Server encontrou% d ocorrência (s) de solicitações de e/s demorando mais do que% d segundos para serem concluídas no arquivo [% ls] no banco de dados `[%ls] (%d)` .</span><span class="sxs-lookup"><span data-stu-id="bdc0c-115">SQL Server has encountered %d occurrence(s) of I/O requests taking longer than %d seconds to complete on file [%ls] in database`[%ls] (%d)`.</span></span>  <span data-ttu-id="bdc0c-116">O identificador de arquivo do SO é 0x%p.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-116">The OS file handle is 0x%p.</span></span>  <span data-ttu-id="bdc0c-117">O deslocamento da E/S mais demorada é: %#016I64x.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-117">The offset of the latest long I/O is: %#016I64x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bdc0c-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="bdc0c-118">Explanation</span></span>  
 <span data-ttu-id="bdc0c-119">Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emitiu uma solicitação de leitura ou gravação de disco, e que a solicitação demorou mais de 15 segundos para retornar.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-119">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="bdc0c-120">Esse erro é informado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica um problema com o subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-120">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the IO subsystem.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="bdc0c-121">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="bdc0c-121">Possible Causes</span></span>  
 <span data-ttu-id="bdc0c-122">Esse problema pode ser causado por problemas de desempenho do sistema, erros de hardware, erros de firmware, problemas de driver de dispositivo ou intervenção de driver de filtro no processo de E/S.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-122">This problem can be caused system performance issues, hardware errors, firmware errors, device driver problems, or filter driver intervention in the IO process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdc0c-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bdc0c-123">User Action</span></span>  
 <span data-ttu-id="bdc0c-124">Solucione este erro procurando mensagens de erros relacionados a hardware no log de eventos de sistema.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-124">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="bdc0c-125">Examine também os logs específicos do hardware, se estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-125">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="bdc0c-126">Use o Monitor de Desempenho para examinar os seguintes contadores:</span><span class="sxs-lookup"><span data-stu-id="bdc0c-126">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="bdc0c-127">**Média de seg/transferência do disco**</span><span class="sxs-lookup"><span data-stu-id="bdc0c-127">**Average Disk Sec/Transfer**</span></span>  
  
-   <span data-ttu-id="bdc0c-128">**Média de comprimento da fila do disco**</span><span class="sxs-lookup"><span data-stu-id="bdc0c-128">**Average Disk Queue Length**</span></span>  
  
-   <span data-ttu-id="bdc0c-129">**Comprimento atual da fila do disco**</span><span class="sxs-lookup"><span data-stu-id="bdc0c-129">**Current Disk Queue Length**</span></span>  
  
 <span data-ttu-id="bdc0c-130">Por exemplo, o tempo da **Média de seg/transferência do disco** em um computador que está executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], normalmente, é inferior a 15 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-130">For example, the **Average Disk Sec/Transfer** time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="bdc0c-131">Se o valor da **Média de seg/transferência do disco** aumentar, isso indicará que o subsistema de E/S não está acompanhando a demanda de E/S.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-131">If the **Average Disk Sec/Transfer** value increases, this indicates that the I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdc0c-132">O acesso ao disco pode ficar mais lento devido a um programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-132">Disk access can be slowed by an antivirus program.</span></span> <span data-ttu-id="bdc0c-133">Para aumentar a velocidade de acesso, exclua os arquivos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificados na mensagem de erro das verificações ativas de vírus.</span><span class="sxs-lookup"><span data-stu-id="bdc0c-133">To increase access speed, exclude the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files that are specified in the error message from active virus scans.</span></span>  
  
 <span data-ttu-id="bdc0c-134">Para obter mais informações sobre erros de E/S, consulte [Noções básicas de E/S do Microsoft SQL Server, Capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) e o artigo da Base de Dados de Conhecimento em [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span><span class="sxs-lookup"><span data-stu-id="bdc0c-134">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) and the Knowledge Base article at [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span></span>  
  
  
