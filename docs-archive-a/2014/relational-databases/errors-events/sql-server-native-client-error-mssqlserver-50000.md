---
title: MSSQLSERVER_50000 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680958"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="b2ed2-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="b2ed2-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="b2ed2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b2ed2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2ed2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b2ed2-104">Product Name</span></span>|<span data-ttu-id="b2ed2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2ed2-105">SQL Server</span></span>|  
|<span data-ttu-id="b2ed2-106">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="b2ed2-106">Product Version</span></span>|<span data-ttu-id="b2ed2-107">11.0</span><span class="sxs-lookup"><span data-stu-id="b2ed2-107">11.0</span></span>|  
|<span data-ttu-id="b2ed2-108">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b2ed2-108">Event ID</span></span>|<span data-ttu-id="b2ed2-109">50000</span><span class="sxs-lookup"><span data-stu-id="b2ed2-109">50000</span></span>|  
|<span data-ttu-id="b2ed2-110">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b2ed2-110">Event Source</span></span>|<span data-ttu-id="b2ed2-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="b2ed2-111">SETUP</span></span>|  
|<span data-ttu-id="b2ed2-112">Componente</span><span class="sxs-lookup"><span data-stu-id="b2ed2-112">Component</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b2ed2-113">Native Client</span><span class="sxs-lookup"><span data-stu-id="b2ed2-113">Native Client</span></span>|  
|<span data-ttu-id="b2ed2-114">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b2ed2-114">Symbolic Name</span></span>||  
|<span data-ttu-id="b2ed2-115">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b2ed2-115">Message Text</span></span>|<span data-ttu-id="b2ed2-116">Ocorreu um erro de rede ao tentar ler a partir do arquivo '%. \* ls'.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2ed2-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="b2ed2-117">Explanation</span></span>  
 <span data-ttu-id="b2ed2-118">Foi feita uma tentativa de instalar (ou atualizar) o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client em um computador onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client já foi instalado e onde a instalação existente era de um arquivo MSI que foi renomeado de sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2ed2-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b2ed2-119">User Action</span></span>  
 <span data-ttu-id="b2ed2-120">Para resolver este erro, desinstale a versão existente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="b2ed2-121">Para evitar esse erro, não instale o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client de um arquivo MSI que não seja denominado sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="b2ed2-122">Somente interno</span><span class="sxs-lookup"><span data-stu-id="b2ed2-122">Internal-Only</span></span>  
  
