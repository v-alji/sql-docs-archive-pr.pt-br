---
title: Publicar um banco de dados (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573101"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="2b361-102">Publicar um banco de dados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2b361-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2b361-103">Você pode usar o **Assistente para Gerar e Publicar Scripts** para publicar um banco de dados inteiro ou objetos de banco de dados individuais em um provedor de hospedagem Web.</span><span class="sxs-lookup"><span data-stu-id="2b361-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b361-104">A funcionalidade descrita neste tópico costumava ser fornecida pelo Assistente de Publicação do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="2b361-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="2b361-105">A funcionalidade de publicação foi adicionada ao Assistente para Gerar e Publicar Scripts; o Assistente de Publicação do Banco de Dados foi descontinuado.</span><span class="sxs-lookup"><span data-stu-id="2b361-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="2b361-106">Assistente para Gerar e Publicar Scripts</span><span class="sxs-lookup"><span data-stu-id="2b361-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="2b361-107">O Assistente para Gerar e Publicar Scripts pode ser usado para publicar um banco de dados ou objetos de banco de dados selecionados em um provedor de hospedagem Web.</span><span class="sxs-lookup"><span data-stu-id="2b361-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="2b361-108">Um provedor de hospedagem Web do SQL Server é uma interface de conectividade com um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2b361-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="2b361-109">O serviço Web é criado usando o projeto dos Serviços de Publicação de Banco de dados do Conjunto de Ferramentas de Hospedagem do SQL Server no CodePlex.</span><span class="sxs-lookup"><span data-stu-id="2b361-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="2b361-110">O serviço Web permite que clientes do hoster da Web publiquem com facilidade seus bancos de dados para o serviço usando o Assistente para Gerar e Publicar Scripts.</span><span class="sxs-lookup"><span data-stu-id="2b361-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="2b361-111">Para obter mais informações sobre como baixar o Conjunto de Ferramentas de Hospedagem do SQL Server, consulte [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="2b361-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="2b361-112">O Assistente para Gerar e Publicar Scripts também pode ser usado para criar um script para transferir um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b361-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="2b361-113">Para publicar um banco de dados em um serviço Web</span><span class="sxs-lookup"><span data-stu-id="2b361-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="2b361-114">No Pesquisador de Objetos, expanda **Banco de Dados**, clique com o botão direito do mouse em um banco de dados, aponte para **Tarefas**e clique em **Gerar e Publicar Scripts**.</span><span class="sxs-lookup"><span data-stu-id="2b361-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="2b361-115">Siga as etapas no assistente para executar scripts nos objetos de banco de dados para publicação.</span><span class="sxs-lookup"><span data-stu-id="2b361-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="2b361-116">Na página **Escolher Objetos** , selecione os objetos a serem publicados no serviço Web de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="2b361-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="2b361-117">Na página **Definir Opções de Script** , selecione **Publicar no Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="2b361-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="2b361-118">Na caixa **Provedor** , especifique o provedor para seu serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2b361-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="2b361-119">Se você não configurou um provedor de hospedagem Web, selecione **Gerenciar Provedores** e use a caixa de diálogo **Gerenciar Provedores** para configurar um provedor para seu serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2b361-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="2b361-120">Para especificar opções de publicação avançadas, selecione o botão **Avançado** na seção **Publicar no serviço Web** .</span><span class="sxs-lookup"><span data-stu-id="2b361-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="2b361-121">Na página **Resumo** , revise suas seleções.</span><span class="sxs-lookup"><span data-stu-id="2b361-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="2b361-122">Clique em **Anterior** para alterar suas seleções.</span><span class="sxs-lookup"><span data-stu-id="2b361-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="2b361-123">Clique em **Próximo** para publicar os objetos selecionados.</span><span class="sxs-lookup"><span data-stu-id="2b361-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="2b361-124">Na página **Salvar ou Publicar Scripts** , monitore o progresso da publicação.</span><span class="sxs-lookup"><span data-stu-id="2b361-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b361-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b361-125">See Also</span></span>  
 <span data-ttu-id="2b361-126">[Gerar scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="2b361-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="2b361-127">Copiar bancos de dados para outros servidores</span><span class="sxs-lookup"><span data-stu-id="2b361-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
