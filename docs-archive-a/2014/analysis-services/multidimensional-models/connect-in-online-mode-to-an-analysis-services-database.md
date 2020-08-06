---
title: Conectar-se no modo online a um banco de dados Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 363beb7132eae92907198979fe2d9892c5d07b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683788"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a><span data-ttu-id="fd543-102">Conectar em Modo Online a um Banco de Dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fd543-102">Connect in Online Mode to an Analysis Services Database</span></span>
  <span data-ttu-id="fd543-103">Você pode se conectar diretamente a um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados existente e modificar os objetos diretamente dentro desse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fd543-103">You can connect directly to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and directly modify objects within that database.</span></span> <span data-ttu-id="fd543-104">Quando você se conecta diretamente a um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , as alterações feitas nos objetos ocorrem de imediato e nenhum projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é criado no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd543-104">When you connect directly to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, changes to objects occur immediately and no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is created within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a><span data-ttu-id="fd543-105">Conectar-se diretamente a um banco de dados do Analysis Services usando as Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd543-105">To Connect Directly to an Analysis Services Database by using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="fd543-106">Abra o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd543-106">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd543-107">No menu **Arquivo** , aponte para **Abrir** e, em seguida, clique em **Banco de Dados do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="fd543-107">On the **File** menu, point to **Open** and then click **Analysis Services Database**.</span></span>  
  
3.  <span data-ttu-id="fd543-108">Selecione **Conectar a banco de dados existente**.</span><span class="sxs-lookup"><span data-stu-id="fd543-108">Select **Connect to existing database**.</span></span>  
  
4.  <span data-ttu-id="fd543-109">Especifique o nome do servidor e do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fd543-109">Specify the server name and the database name.</span></span>  
  
     <span data-ttu-id="fd543-110">Você pode digitar o nome de banco de dados ou consultar o servidor para exibir os bancos de dados existentes nele.</span><span class="sxs-lookup"><span data-stu-id="fd543-110">You can either type the database name or query the server to view the existing databases on the server.</span></span>  
  
5.  <span data-ttu-id="fd543-111">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd543-111">Click **OK**.</span></span>  
  
     <span data-ttu-id="fd543-112">Agora, você pode editar diretamente qualquer objeto do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd543-112">You can now directly edit any objects within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd543-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd543-113">See Also</span></span>  
 <span data-ttu-id="fd543-114">[Trabalhando com projetos Analysis Services e bancos de dados durante a fase de desenvolvimento](work-with-analysis-services-projects-and-databases-in-development.md) </span><span class="sxs-lookup"><span data-stu-id="fd543-114">[Working with Analysis Services Projects and Databases During the Development Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span></span>  
 [<span data-ttu-id="fd543-115">Criação de modelos multidimensionais usando o SSDT &#40;SQL Server Data Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fd543-115">Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;</span></span>](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  
