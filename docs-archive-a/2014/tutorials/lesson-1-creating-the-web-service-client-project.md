---
title: 'Lição 1: criando o projeto do cliente do serviço Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681971"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="94955-102">Lição 1: Criando o serviço Web Projeto de Cliente</span><span class="sxs-lookup"><span data-stu-id="94955-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="94955-103">Para este passo a passo, você criará um aplicativo de console simples que acessa o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="94955-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="94955-104">Este passo a passo pressupõe que você está desenvolvendo no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94955-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="94955-105">Para criar um aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="94955-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="94955-106">No menu **arquivo** , aponte para **novo**e clique em **projeto** para abrir a caixa de diálogo **novo projeto** .</span><span class="sxs-lookup"><span data-stu-id="94955-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="94955-107">No painel esquerdo, em **modelos instalados**, clique em **Visual Basic** ou no nó **Visual C#** e selecione uma categoria de tipos de projeto na lista expandida.</span><span class="sxs-lookup"><span data-stu-id="94955-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="94955-108">Escolha o tipo de projeto de **aplicativo de console** .</span><span class="sxs-lookup"><span data-stu-id="94955-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="94955-109">Na caixa **nome** , insira um nome para o seu projeto.</span><span class="sxs-lookup"><span data-stu-id="94955-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="94955-110">Digite o nome `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="94955-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="94955-111">Na caixa **local** , insira o caminho onde você deseja salvar o projeto ou clique em **procurar** para navegar até a pasta.</span><span class="sxs-lookup"><span data-stu-id="94955-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="94955-112">Uma exibição recolhida do seu projeto é exibida no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="94955-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="94955-113">No Gerenciador de Soluções, expanda o nó do projeto.</span><span class="sxs-lookup"><span data-stu-id="94955-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="94955-114">Um arquivo com o nome padrão de Program.cs (Module1. vb para [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) foi adicionado ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="94955-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94955-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94955-115">See Also</span></span>  
 <span data-ttu-id="94955-116">[Lição 2: adicionando uma referência Web](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="94955-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="94955-117">Acessando o serviço Web servidor de relatórios usando Visual Basic ou o tutorial&#35; &#40;do SSRS do Visual C&#41;</span><span class="sxs-lookup"><span data-stu-id="94955-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
