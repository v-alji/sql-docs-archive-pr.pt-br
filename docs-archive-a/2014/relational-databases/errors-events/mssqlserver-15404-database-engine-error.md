---
title: MSSQLSERVER_15404 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581894"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="081e6-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="081e6-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="081e6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="081e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="081e6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="081e6-104">Product Name</span></span>|<span data-ttu-id="081e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="081e6-105">SQL Server</span></span>|  
|<span data-ttu-id="081e6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="081e6-106">Event ID</span></span>|<span data-ttu-id="081e6-107">15404</span><span class="sxs-lookup"><span data-stu-id="081e6-107">15404</span></span>|  
|<span data-ttu-id="081e6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="081e6-108">Event Source</span></span>|<span data-ttu-id="081e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="081e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="081e6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="081e6-110">Component</span></span>|<span data-ttu-id="081e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="081e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="081e6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="081e6-112">Symbolic Name</span></span>|<span data-ttu-id="081e6-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="081e6-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="081e6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="081e6-114">Message Text</span></span>|<span data-ttu-id="081e6-115">Não foi possível obter informações sobre o grupo/usuário '*user*' do Windows NT, código de erro *code*.</span><span class="sxs-lookup"><span data-stu-id="081e6-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="081e6-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="081e6-116">Explanation</span></span>  
 <span data-ttu-id="081e6-117">15404 é usado na autenticação quando uma entidade de segurança inválida é especificada.</span><span class="sxs-lookup"><span data-stu-id="081e6-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="081e6-118">A representação de uma conta do Windows falha porque não há uma relação de confiança total entre a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o domínio da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="081e6-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="081e6-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="081e6-119">User Action</span></span>  
 <span data-ttu-id="081e6-120">Verifique se a entidade de segurança do Windows existe e não está digitada de forma incorreta.</span><span class="sxs-lookup"><span data-stu-id="081e6-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="081e6-121">Se esse erro for resultante da falta de uma relação de confiança total entre a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o domínio da conta do Windows, uma destas ações poderá corrigir o erro:</span><span class="sxs-lookup"><span data-stu-id="081e6-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="081e6-122">Use uma conta do mesmo domínio que o usuário do Windows para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="081e6-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="081e6-123">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver usando uma conta de computador como Serviço de Rede ou Sistema Local, o computador deverá ser confiável no domínio que contém o usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="081e6-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="081e6-124">Usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="081e6-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
