---
title: Contas de serviço (Assistente para Configurar Segurança de Espelhamento de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681143"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="3b741-102">Contas de Serviço (Assistente para Configurar Segurança de Espelhamento do Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="3b741-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="3b741-103">Ao usar a Autenticação do Windows, se as instâncias de servidor usarem contas diferentes, especifique as contas de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b741-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3b741-104">Essas contas de serviço devem ser todas contas de domínio (nos mesmos domínios ou domínios confiáveis).</span><span class="sxs-lookup"><span data-stu-id="3b741-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="3b741-105">Se todas as instâncias de servidor usarem a mesma conta de domínio ou autenticação com base em certificação, deixe os campos em branco.</span><span class="sxs-lookup"><span data-stu-id="3b741-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="3b741-106">Basta clicar em **Concluir**e o assistente configurará automaticamente as contas com base na conta do assistente atual.</span><span class="sxs-lookup"><span data-stu-id="3b741-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3b741-107">Se os pontos de extremidade do espelhamento de banco de dados das instâncias de servidor estiverem configurados para usar certificados, então os campos de conta de serviço devem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="3b741-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="3b741-108">**Para configurar o espelhamento de banco de dados usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3b741-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="3b741-109">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3b741-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="3b741-110">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3b741-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="3b741-111">Opções</span><span class="sxs-lookup"><span data-stu-id="3b741-111">Options</span></span>  
 <span data-ttu-id="3b741-112">**Principal**</span><span class="sxs-lookup"><span data-stu-id="3b741-112">**Principal**</span></span>  
 <span data-ttu-id="3b741-113">Especifique a conta de serviço da instância de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="3b741-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="3b741-114">Digite o nome de domínio em letras maiúsculas:</span><span class="sxs-lookup"><span data-stu-id="3b741-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="3b741-115">*Nome_do_domínio* \\ *nome de usuário*</span><span class="sxs-lookup"><span data-stu-id="3b741-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="3b741-116">**Espelho**</span><span class="sxs-lookup"><span data-stu-id="3b741-116">**Mirror**</span></span>  
 <span data-ttu-id="3b741-117">Especifique a conta de serviço da instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="3b741-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="3b741-118">Digite o nome de domínio em letras maiúsculas:</span><span class="sxs-lookup"><span data-stu-id="3b741-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="3b741-119">*Nome_do_domínio* \\ *nome de usuário*</span><span class="sxs-lookup"><span data-stu-id="3b741-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="3b741-120">**Testemunha**</span><span class="sxs-lookup"><span data-stu-id="3b741-120">**Witness**</span></span>  
 <span data-ttu-id="3b741-121">Especifique a conta de serviço da instância de servidor testemunha.</span><span class="sxs-lookup"><span data-stu-id="3b741-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="3b741-122">Digite o nome de domínio em letras maiúsculas:</span><span class="sxs-lookup"><span data-stu-id="3b741-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="3b741-123">*Nome_do_domínio* \\ *nome de usuário*</span><span class="sxs-lookup"><span data-stu-id="3b741-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b741-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b741-124">See Also</span></span>  
 <span data-ttu-id="3b741-125">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="3b741-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="3b741-126">[Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3b741-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="3b741-127">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b741-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="3b741-128">Configurar contas de logon para espelhamento de banco de dados ou Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b741-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
