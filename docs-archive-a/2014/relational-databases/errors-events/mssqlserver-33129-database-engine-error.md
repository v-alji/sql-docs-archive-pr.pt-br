---
title: MSSQLSERVER_33129 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573060"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="25d1d-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="25d1d-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="25d1d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="25d1d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25d1d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="25d1d-104">Product Name</span></span>|<span data-ttu-id="25d1d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25d1d-105">SQL Server</span></span>|  
|<span data-ttu-id="25d1d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="25d1d-106">Event ID</span></span>|<span data-ttu-id="25d1d-107">33129</span><span class="sxs-lookup"><span data-stu-id="25d1d-107">33129</span></span>|  
|<span data-ttu-id="25d1d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="25d1d-108">Event Source</span></span>|<span data-ttu-id="25d1d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25d1d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25d1d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="25d1d-110">Component</span></span>|<span data-ttu-id="25d1d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25d1d-111">SQLEngine</span></span>|  
|<span data-ttu-id="25d1d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="25d1d-112">Symbolic Name</span></span>|<span data-ttu-id="25d1d-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="25d1d-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="25d1d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="25d1d-114">Message Text</span></span>|<span data-ttu-id="25d1d-115">Não é possível usar ALTER_LOGIN com o argumento DISABLE para negar acesso a um grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="25d1d-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25d1d-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="25d1d-116">Explanation</span></span>  
 <span data-ttu-id="25d1d-117">Esta mensagem ocorre na tentativa de desabilitar o logon de um Grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="25d1d-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25d1d-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="25d1d-118">User Action</span></span>  
 <span data-ttu-id="25d1d-119">O logon de um Grupo do Windows não pode ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="25d1d-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="25d1d-120">Para remover temporariamente a permissão de acesso concedida a um Grupo do Windows, revogue (REVOKE) a permissão CONNECT do logon para o Grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="25d1d-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="25d1d-121">Os usuários do Windows possivelmente ainda deverão ter acesso por meio do logon individual ou através de outro Grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="25d1d-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="25d1d-122">O exemplo a seguir revoga a permissão connect no Grupo de Contabilidade do domínio WESTCOAST.</span><span class="sxs-lookup"><span data-stu-id="25d1d-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
