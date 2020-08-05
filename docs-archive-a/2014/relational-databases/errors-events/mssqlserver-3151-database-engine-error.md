---
title: MSSQLSERVER_3151 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574032"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="aab71-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="aab71-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="aab71-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aab71-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aab71-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="aab71-104">Product Name</span></span>|<span data-ttu-id="aab71-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aab71-105">SQL Server</span></span>|  
|<span data-ttu-id="aab71-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="aab71-106">Event ID</span></span>|<span data-ttu-id="aab71-107">3151</span><span class="sxs-lookup"><span data-stu-id="aab71-107">3151</span></span>|  
|<span data-ttu-id="aab71-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="aab71-108">Event Source</span></span>|<span data-ttu-id="aab71-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aab71-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aab71-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aab71-110">Component</span></span>|<span data-ttu-id="aab71-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aab71-111">SQLEngine</span></span>|  
|<span data-ttu-id="aab71-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="aab71-112">Symbolic Name</span></span>|<span data-ttu-id="aab71-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="aab71-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="aab71-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="aab71-114">Message Text</span></span>|<span data-ttu-id="aab71-115">Falha ao restaurar o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="aab71-115">Failed to restore master database.</span></span> <span data-ttu-id="aab71-116">Desligando o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aab71-116">Shutting down SQL Server.</span></span> <span data-ttu-id="aab71-117">Verifique os logs de erros e recrie o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="aab71-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="aab71-118">Para obter mais informações sobre como recriar o banco de dados mestre, consulte os Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aab71-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aab71-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="aab71-119">Explanation</span></span>  
 <span data-ttu-id="aab71-120">Essa é uma mensagem de erro geral que indica vários problemas com o banco de dados **mestre**.</span><span class="sxs-lookup"><span data-stu-id="aab71-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aab71-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="aab71-121">User Action</span></span>  
 <span data-ttu-id="aab71-122">Verifique os logs de erros para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aab71-122">Check the error logs for more information.</span></span> <span data-ttu-id="aab71-123">Para criar um banco de dados **mestre** utilizável, execute Setup.exe com a opção REBUILDDATABASE.</span><span class="sxs-lookup"><span data-stu-id="aab71-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="aab71-124">Para saber mais, consulte "Como: instalar o SQL Server a partir do prompt de comando” nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aab71-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
