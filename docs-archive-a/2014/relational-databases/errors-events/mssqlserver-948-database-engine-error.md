---
title: MSSQLSERVER_948 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573040"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="42c85-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="42c85-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="42c85-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="42c85-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42c85-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="42c85-104">Product Name</span></span>|<span data-ttu-id="42c85-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42c85-105">SQL Server</span></span>|  
|<span data-ttu-id="42c85-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="42c85-106">Event ID</span></span>|<span data-ttu-id="42c85-107">948</span><span class="sxs-lookup"><span data-stu-id="42c85-107">948</span></span>|  
|<span data-ttu-id="42c85-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="42c85-108">Event Source</span></span>|<span data-ttu-id="42c85-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42c85-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42c85-110">Componente</span><span class="sxs-lookup"><span data-stu-id="42c85-110">Component</span></span>|<span data-ttu-id="42c85-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42c85-111">SQLEngine</span></span>|  
|<span data-ttu-id="42c85-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="42c85-112">Symbolic Name</span></span>|<span data-ttu-id="42c85-113">NA</span><span class="sxs-lookup"><span data-stu-id="42c85-113">NA</span></span>|  
|<span data-ttu-id="42c85-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="42c85-114">Message Text</span></span>|<span data-ttu-id="42c85-115">O banco de dados '%.\*ls' não pode ser aberto porque sua versão é a %d.</span><span class="sxs-lookup"><span data-stu-id="42c85-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="42c85-116">Esse servidor oferece suporte à versão %d e anteriores.</span><span class="sxs-lookup"><span data-stu-id="42c85-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="42c85-117">Não há suporte para um caminho de downgrade.</span><span class="sxs-lookup"><span data-stu-id="42c85-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42c85-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="42c85-118">Explanation</span></span>  
 <span data-ttu-id="42c85-119">Determinados recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afetam a estrutura dos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="42c85-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="42c85-120">Quando você anexa um banco de dados a outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível que o formato de arquivo não seja compatível com uma versão diferente do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c85-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="42c85-121">Por exemplo, esse erro pode ser causado pelo uso de um formato de armazenamento vardecimal em uma versão posterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, depois, pela tentativa de anexar os arquivos de banco de dados a uma versão anterior a do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="42c85-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42c85-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="42c85-122">User Action</span></span>  
 <span data-ttu-id="42c85-123">Determine a versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo executada no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="42c85-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="42c85-124">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique com o botão direito do mouse no servidor e clique em **Propriedades** ou digite `SELECT @@VERSION` em uma janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="42c85-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="42c85-125">Abra o banco de dados usando a versão original do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c85-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="42c85-126">Investigue os recursos habilitados no banco de dados original na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c85-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="42c85-127">Modifique essas configurações para trabalhar com a versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual será anexado o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="42c85-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
