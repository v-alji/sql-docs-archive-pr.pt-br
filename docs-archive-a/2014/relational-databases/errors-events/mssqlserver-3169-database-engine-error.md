---
title: MSSQLSERVER_3169 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574026"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="34057-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="34057-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="34057-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="34057-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34057-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="34057-104">Product Name</span></span>|<span data-ttu-id="34057-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="34057-105">SQL Server</span></span>|  
|<span data-ttu-id="34057-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34057-106">Event ID</span></span>|<span data-ttu-id="34057-107">3169</span><span class="sxs-lookup"><span data-stu-id="34057-107">3169</span></span>|  
|<span data-ttu-id="34057-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="34057-108">Event Source</span></span>|<span data-ttu-id="34057-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="34057-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="34057-110">Componente</span><span class="sxs-lookup"><span data-stu-id="34057-110">Component</span></span>|<span data-ttu-id="34057-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34057-111">SQLEngine</span></span>|  
|<span data-ttu-id="34057-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="34057-112">Symbolic Name</span></span>|<span data-ttu-id="34057-113">NA</span><span class="sxs-lookup"><span data-stu-id="34057-113">NA</span></span>|  
|<span data-ttu-id="34057-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="34057-114">Message Text</span></span>|<span data-ttu-id="34057-115">O backup do banco de dados foi feito em um servidor que executa a versão %ls.</span><span class="sxs-lookup"><span data-stu-id="34057-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="34057-116">Essa versão é incompatível com esse servidor que está executando a versão %ls.</span><span class="sxs-lookup"><span data-stu-id="34057-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="34057-117">Restaure o banco de dados em um servidor que dê suporte ao backup ou use um backup compatível com esse servidor.</span><span class="sxs-lookup"><span data-stu-id="34057-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34057-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="34057-118">Explanation</span></span>  
 <span data-ttu-id="34057-119">Determinados recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afetam a estrutura dos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="34057-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="34057-120">Quando você restaura um banco de dados em outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível que o formato de arquivo não seja compatível com uma versão diferente do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34057-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="34057-121">Por exemplo, esse erro pode ser causado pelo uso do formato vardecimalstorage em uma versão posterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, em seguida, pela tentativa de restaurar os arquivos de banco de dados em uma versão anterior ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="34057-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34057-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="34057-122">User Action</span></span>  
 <span data-ttu-id="34057-123">Determine a versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo executada no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="34057-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="34057-124">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique com o botão direito do mouse no servidor e clique em **Propriedades** ou digite `SELECT @@VERSION` em uma janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="34057-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="34057-125">Abra o banco de dados usando a versão original do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34057-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="34057-126">Investigue os recursos habilitados no banco de dados original na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34057-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="34057-127">Modifique essas configurações para funcionarem com a versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual o banco de dados será restaurado.</span><span class="sxs-lookup"><span data-stu-id="34057-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
