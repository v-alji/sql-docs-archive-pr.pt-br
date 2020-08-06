---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575150"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="707b0-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="707b0-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="707b0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="707b0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="707b0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="707b0-104">Product Name</span></span>|<span data-ttu-id="707b0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="707b0-105">SQL Server</span></span>|  
|<span data-ttu-id="707b0-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="707b0-106">Event ID</span></span>|<span data-ttu-id="707b0-107">18452</span><span class="sxs-lookup"><span data-stu-id="707b0-107">18452</span></span>|  
|<span data-ttu-id="707b0-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="707b0-108">Event Source</span></span>|<span data-ttu-id="707b0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="707b0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="707b0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="707b0-110">Component</span></span>|<span data-ttu-id="707b0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="707b0-111">SQLEngine</span></span>|  
|<span data-ttu-id="707b0-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="707b0-112">Symbolic Name</span></span>|<span data-ttu-id="707b0-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="707b0-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="707b0-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="707b0-114">Message Text</span></span>|<span data-ttu-id="707b0-115">Falha no logon do usuário '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="707b0-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="707b0-116">O logon é um logon do SQL Server e não pode ser usado com a Autenticação do Windows.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="707b0-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="707b0-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="707b0-117">Explanation</span></span>  
 <span data-ttu-id="707b0-118">O usuário tentou fazer logon com credenciais que não podem ser validadas.</span><span class="sxs-lookup"><span data-stu-id="707b0-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="707b0-119">Causas possíveis:</span><span class="sxs-lookup"><span data-stu-id="707b0-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="707b0-120">O logon pode ser um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o servidor aceita somente a Autenticação do Windows (Segurança Integrada).</span><span class="sxs-lookup"><span data-stu-id="707b0-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="707b0-121">Você está tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o logon usado não existe no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="707b0-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="707b0-122">O logon pode usar a Autenticação do Windows (Segurança Integrada), mas é uma entidade não reconhecida do Windows.</span><span class="sxs-lookup"><span data-stu-id="707b0-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="707b0-123">Uma entidade não reconhecida do Windows significa que o logon não pode ser verificado pelo Windows.</span><span class="sxs-lookup"><span data-stu-id="707b0-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="707b0-124">Talvez isso ocorra porque o logon do Windows é de um domínio não confiável.</span><span class="sxs-lookup"><span data-stu-id="707b0-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="707b0-125">Problemas semelhantes podem causar o erro menos específico 18456.</span><span class="sxs-lookup"><span data-stu-id="707b0-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="707b0-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="707b0-126">User Action</span></span>  
 <span data-ttu-id="707b0-127">Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado no Modo de Autenticação Mista.</span><span class="sxs-lookup"><span data-stu-id="707b0-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="707b0-128">Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe.</span><span class="sxs-lookup"><span data-stu-id="707b0-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="707b0-129">Se você estiver tentando se conectar usando a Autenticação do Windows, verifique se está devidamente conectado no domínio correto.</span><span class="sxs-lookup"><span data-stu-id="707b0-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
