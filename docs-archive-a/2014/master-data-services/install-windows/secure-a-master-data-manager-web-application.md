---
title: Proteger um aplicativo Web Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684253"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="60b77-102">Proteger um aplicativo Web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="60b77-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="60b77-103">Você pode proteger o aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] com HTTPS.</span><span class="sxs-lookup"><span data-stu-id="60b77-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60b77-104">O aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] pode usar HTTP ou HTTPS, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="60b77-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60b77-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="60b77-105">Prerequisites</span></span>  
 <span data-ttu-id="60b77-106">Para executar o procedimento:</span><span class="sxs-lookup"><span data-stu-id="60b77-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="60b77-107">Você deve ser um administrador no servidor Web onde o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] é instalado.</span><span class="sxs-lookup"><span data-stu-id="60b77-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="60b77-108">O MDS deve ser instalado no servidor Web e um aplicativo Web deve existir.</span><span class="sxs-lookup"><span data-stu-id="60b77-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="60b77-109">Para obter mais informações, veja [Instalar o Master Data Services](install-master-data-services.md) e [Criar um aplicativo Web do Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60b77-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="60b77-110">Para proteger o aplicativo Web Master Data Manager com HTTPS</span><span class="sxs-lookup"><span data-stu-id="60b77-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="60b77-111">Depois que você confirmar que o aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] está configurado corretamente com HTTP, crie um certificado no IIS.</span><span class="sxs-lookup"><span data-stu-id="60b77-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="60b77-112">Para obter mais informações, consulte [Configurando certificados de servidor no IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="60b77-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="60b77-113">No painel **Conexões** , em **Sites**, clique no site que hospeda o aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60b77-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="60b77-114">No painel **Ações**, clique em **Associações**.</span><span class="sxs-lookup"><span data-stu-id="60b77-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="60b77-115">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60b77-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="60b77-116">Na lista, selecione **https**.</span><span class="sxs-lookup"><span data-stu-id="60b77-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="60b77-117">Selecione o certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="60b77-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="60b77-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60b77-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="60b77-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="60b77-119">Optional.</span></span> <span data-ttu-id="60b77-120">Para remover o HTTP de forma que os usuários só possam acessar o site com HTTPS, na lista, clique na linha com **http**.</span><span class="sxs-lookup"><span data-stu-id="60b77-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="60b77-121">Clique em **Remover** e, na caixa de diálogo de confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="60b77-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="60b77-122">Você deve alterar as configurações basicHttp e de wsHttpBinding depois de remover o HTTP.</span><span class="sxs-lookup"><span data-stu-id="60b77-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="60b77-123">Para fechar a caixa de diálogo **Associações de Site** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="60b77-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="60b77-124">Agora, abra o arquivo web.config de *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span><span class="sxs-lookup"><span data-stu-id="60b77-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="60b77-125">Localize a cadeia de caracteres `<security mode="Message">` e altere-a para `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="60b77-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="60b77-126">Salve e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="60b77-126">Save and close the file.</span></span> <span data-ttu-id="60b77-127">Se você receber um erro, pode ser porque o UAC está habilitado.</span><span class="sxs-lookup"><span data-stu-id="60b77-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="60b77-128">Para obter mais informações, consulte [Desativar o controle de conta do usuário](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="60b77-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="60b77-129">Agora, os usuários devem ser capazes de usar HTTPS para acessar o site.</span><span class="sxs-lookup"><span data-stu-id="60b77-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b77-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b77-130">See Also</span></span>  
 [<span data-ttu-id="60b77-131">Criar um aplicativo Web do Master Data Manager &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="60b77-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
