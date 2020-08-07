---
title: Propriedades do SQL Server Agent (página Sistema de Trabalho) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582251"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="3cdb8-102">Propriedades do SQL Server Agent (página Sistema de Trabalho)</span><span class="sxs-lookup"><span data-stu-id="3cdb8-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="3cdb8-103">Use esta página para exibir e modificar como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviço Agent gerencia trabalhos.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3cdb8-104">Opções</span><span class="sxs-lookup"><span data-stu-id="3cdb8-104">Options</span></span>  
 <span data-ttu-id="3cdb8-105">**Intervalo de tempo limite de desligamento (em segundos)**</span><span class="sxs-lookup"><span data-stu-id="3cdb8-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="3cdb8-106">Especifica o número de segundos que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent espera os trabalhos serem concluídos antes de desligar.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="3cdb8-107">Se o trabalho ainda estiver em execução depois do intervalo especificado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para o trabalho à força.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="3cdb8-108">**Usar uma conta proxy não administrador**</span><span class="sxs-lookup"><span data-stu-id="3cdb8-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="3cdb8-109">Define uma conta proxy não administrador para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="3cdb8-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]e versões posteriores dão suporte a vários proxies, portanto, essa opção só é aplicável ao gerenciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versões do agente anteriores ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cdb8-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="3cdb8-111">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="3cdb8-111">**User name**</span></span>  
 <span data-ttu-id="3cdb8-112">Digite o nome do usuário para a conta proxy não administrador.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3cdb8-113">dá suporte a vários proxies; portanto, essa opção será aplicável somente ao gerenciar versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent anteriores ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cdb8-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="3cdb8-114">**Senha**</span><span class="sxs-lookup"><span data-stu-id="3cdb8-114">**Password**</span></span>  
 <span data-ttu-id="3cdb8-115">Digite a senha do usuário para a conta proxy não administrador.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="3cdb8-116">e as versões posteriores dão suporte a vários proxies; portanto, essa opção será aplicável somente ao gerenciar versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent anteriores ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cdb8-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="3cdb8-117">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="3cdb8-117">**Domain**</span></span>  
 <span data-ttu-id="3cdb8-118">Digite o domínio do usuário para a conta proxy não administrador.</span><span class="sxs-lookup"><span data-stu-id="3cdb8-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3cdb8-119">dá suporte a vários proxies; portanto, essa opção será aplicável somente ao gerenciar versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent anteriores ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cdb8-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdb8-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3cdb8-120">See Also</span></span>  
 [<span data-ttu-id="3cdb8-121">Implementar trabalhos</span><span class="sxs-lookup"><span data-stu-id="3cdb8-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
