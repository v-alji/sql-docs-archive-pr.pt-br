---
title: Reporting Services a autenticação do modo do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683932"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="8874f-102">Reporting Services no modo de autenticação do SharePoint</span><span class="sxs-lookup"><span data-stu-id="8874f-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="8874f-103">Use a página **Autenticação do modo do SharePoint do Reporting Services** do Assistente de instalação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para especificar as credenciais da conta do serviço que é usado na instalação atual do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8874f-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="8874f-104">As credenciais serão usadas para criar um novo pool de aplicativos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8874f-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="8874f-105">Além disso, um novo aplicativo de serviço SharePoint do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] será criado.</span><span class="sxs-lookup"><span data-stu-id="8874f-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="8874f-106">O nome do aplicativo de serviço conterá o nome da instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] anterior.</span><span class="sxs-lookup"><span data-stu-id="8874f-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8874f-107">Opções</span><span class="sxs-lookup"><span data-stu-id="8874f-107">Options</span></span>  
  
-   <span data-ttu-id="8874f-108">A opção **Nome da conta do pool de aplicativos do SSRS:** é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8874f-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="8874f-109">O valor é automaticamente populado com o valor atual da instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] existente que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="8874f-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="8874f-110">A opção **Senha da conta do pool de aplicativos do SSRS:** será desabilitada se a conta do pool de aplicativos não exigir uma senha.</span><span class="sxs-lookup"><span data-stu-id="8874f-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="8874f-111">Por exemplo, "NT Authority\NetworkService".</span><span class="sxs-lookup"><span data-stu-id="8874f-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="8874f-112">Se a conta do pool de aplicativos exigir uma senha, você só poderá continuar com a atualização se digitar a senha correta.</span><span class="sxs-lookup"><span data-stu-id="8874f-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="8874f-113">Para obter mais informações, consulte [atualizar e migrar Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) ( https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="8874f-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8874f-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8874f-114">See Also</span></span>  
 [<span data-ttu-id="8874f-115">Atualizar e migrar o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8874f-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
