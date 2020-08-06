---
title: Testar permissões de um usuário (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574751"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="96386-102">Testar permissões de um usuário (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="96386-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="96386-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode criar um usuário de teste e registrar em log no aplicativo Web para testar permissions. Quando um usuário tenta acessar a URL [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , as credenciais do usuário são autenticadas.</span><span class="sxs-lookup"><span data-stu-id="96386-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="96386-104">No Internet Explorer, as configurações de segurança controlam se isso ocorre automaticamente ou se o usuário deve inserir nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="96386-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="96386-105">Para alterar essas configurações, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="96386-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="96386-106">Para testar a segurança de um usuário</span><span class="sxs-lookup"><span data-stu-id="96386-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="96386-107">No Internet Explorer 7 e posterior, clique em **Ferramentas**, em **Opções de Internet**e na guia **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="96386-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="96386-108">Clique em **Intranet Local** e no botão **Nível Personalizado** .</span><span class="sxs-lookup"><span data-stu-id="96386-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="96386-109">Na seção **Autenticação de Usuário** , escolha **Aviso para nome de usuário e senha**.</span><span class="sxs-lookup"><span data-stu-id="96386-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="96386-110">Da próxima vez que você abrir a janela do navegador, será solicitado a fornecer um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="96386-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96386-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96386-111">See Also</span></span>  
 [<span data-ttu-id="96386-112">Segurança &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96386-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
