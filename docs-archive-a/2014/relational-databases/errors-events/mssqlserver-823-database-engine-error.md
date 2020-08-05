---
title: MSSQLSERVER_823 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574000"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="4e080-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="4e080-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="4e080-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4e080-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e080-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4e080-104">Product Name</span></span>|<span data-ttu-id="4e080-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e080-105">SQL Server</span></span>|  
|<span data-ttu-id="4e080-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4e080-106">Event ID</span></span>|<span data-ttu-id="4e080-107">823</span><span class="sxs-lookup"><span data-stu-id="4e080-107">823</span></span>|  
|<span data-ttu-id="4e080-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4e080-108">Event Source</span></span>|<span data-ttu-id="4e080-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4e080-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4e080-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4e080-110">Component</span></span>|<span data-ttu-id="4e080-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4e080-111">SQLEngine</span></span>|  
|<span data-ttu-id="4e080-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4e080-112">Symbolic Name</span></span>|<span data-ttu-id="4e080-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="4e080-113">B_HARDERR</span></span>|  
|<span data-ttu-id="4e080-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4e080-114">Message Text</span></span>|<span data-ttu-id="4e080-115">O sistema operacional retornou o erro %ls para o SQL Server durante um %S_MSG no deslocamento %#016I64x do arquivo '%ls'.</span><span class="sxs-lookup"><span data-stu-id="4e080-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="4e080-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span><span class="sxs-lookup"><span data-stu-id="4e080-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="4e080-117">Essa é uma condição de erro grave em nível de sistema que ameaça a integridade do banco de dados e deve ser corrigida imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4e080-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="4e080-118">Faça uma verificação completa da consistência do banco de dados (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="4e080-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="4e080-119">Esse erro pode ter sido causado por vários fatores. Para obter mais informações, consulte os Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e080-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4e080-120">Explicação</span><span class="sxs-lookup"><span data-stu-id="4e080-120">Explanation</span></span>  
 <span data-ttu-id="4e080-121">Falha de solicitação de leitura ou gravação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4e080-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="4e080-122">O código de erro retornado pelo Windows e o texto correspondente estão inseridos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="4e080-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="4e080-123">No caso de leitura, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] já terá tentado novamente a solicitação de leitura quatro vezes.</span><span class="sxs-lookup"><span data-stu-id="4e080-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="4e080-124">Normalmente, esse erro se deve a um erro de hardware, mas pode ser causado pelo driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4e080-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="4e080-125">Para obter mais informações sobre o erro 823, consulte [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="4e080-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="4e080-126">Para obter mais informações sobre erros de E/S, consulte [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) (Noções básicas de E/S do Microsoft SQL Server, Capítulo 2).</span><span class="sxs-lookup"><span data-stu-id="4e080-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4e080-127">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4e080-127">User Action</span></span>  
 <span data-ttu-id="4e080-128">Verifique se há mais informações no log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="4e080-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="4e080-129">Entre em contato com o fabricante de hardware ou o Atendimento ao Cliente e o Suporte da Microsoft para determinar a causa e ação corretiva.</span><span class="sxs-lookup"><span data-stu-id="4e080-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="4e080-130">Depois que o erro de hardware for corrigido, restaure todos os bancos de dados e execute o DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="4e080-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
