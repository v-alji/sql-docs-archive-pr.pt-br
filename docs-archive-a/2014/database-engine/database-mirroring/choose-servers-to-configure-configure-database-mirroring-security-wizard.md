---
title: Escolher os servidores a serem configurados (Assistente para Configurar Segurança de Espelhamento de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571585"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="606e1-102">Selecionar servidores a configurar (Assistente para Configurar Segurança de Espelhamento de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="606e1-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="606e1-103">Use essa página para especificar quais instâncias de servidor serão configuradas no momento.</span><span class="sxs-lookup"><span data-stu-id="606e1-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="606e1-104">É preciso selecionar no mínimo uma instância de servidor antes de prosseguir com o assistente.</span><span class="sxs-lookup"><span data-stu-id="606e1-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="606e1-105">Se você desmarcar a caixa de seleção de uma instância de servidor, o assistente não fará nenhuma alteração nessa instância.</span><span class="sxs-lookup"><span data-stu-id="606e1-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="606e1-106">O assistente, porém, solicitará que você insira informações sobre essa instância e salvará as informações como parte da configuração das outras instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="606e1-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="606e1-107">Por exemplo, se você desmarcar a caixa de seleção da instância de servidor testemunha, o assistente solicitará a inserção da conta de serviços da testemunha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , uma vez que um logon para essa conta precisará ser criado como parte da configuração de segurança salva nas instâncias do servidor principal e de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="606e1-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="606e1-108">**Para configurar o espelhamento de banco de dados usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="606e1-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="606e1-109">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="606e1-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="606e1-110">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="606e1-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="606e1-111">Opções</span><span class="sxs-lookup"><span data-stu-id="606e1-111">Options</span></span>  
 <span data-ttu-id="606e1-112">**Instância do servidor principal**</span><span class="sxs-lookup"><span data-stu-id="606e1-112">**Principal server instance**</span></span>  
 <span data-ttu-id="606e1-113">Selecione para configurar a segurança do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="606e1-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="606e1-114">**Instância do servidor espelho**</span><span class="sxs-lookup"><span data-stu-id="606e1-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="606e1-115">Selecione para configurar a segurança do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="606e1-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="606e1-116">**Instância do servidor testemunha**</span><span class="sxs-lookup"><span data-stu-id="606e1-116">**Witness server instance**</span></span>  
 <span data-ttu-id="606e1-117">Selecione para configurar segurança para o servidor testemunha (se houver).</span><span class="sxs-lookup"><span data-stu-id="606e1-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606e1-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="606e1-118">See Also</span></span>  
 <span data-ttu-id="606e1-119">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="606e1-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="606e1-120">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="606e1-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
