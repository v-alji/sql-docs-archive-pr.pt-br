---
title: Modificar ou excluir um banco de dados Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684938"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="1eeca-102">Modificar ou excluir um banco de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1eeca-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="1eeca-103">É possível alterar o nome e a descrição de um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] antes da implantação no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e depois da implantação no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eeca-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1eeca-104">Também é possível ajustar configurações adicionais de um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="1eeca-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1eeca-105">Não é possível alterar as propriedades do banco de dados usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em modo online.</span><span class="sxs-lookup"><span data-stu-id="1eeca-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="1eeca-106">Modificando banco de dados usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1eeca-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1eeca-107">Uma vez implantado o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você pode usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para alterar o modo de representação usado pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ao se conectar com as fontes de dados contidas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eeca-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="1eeca-108">O modo de representação permite que você especifique o contexto de segurança usado pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ao tentar conectar-se com uma fonte de dados para fins de processamento, navegação ou detalhamento.</span><span class="sxs-lookup"><span data-stu-id="1eeca-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="1eeca-109">Modificando banco de dados usando as Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1eeca-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="1eeca-110">Use o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em modo de projeto para modificar as traduções de legenda e a descrição de um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usado para definir um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eeca-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="1eeca-111">Para obter mais informações sobre como usar traduções em um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados, consulte [cenários de globalização para Analysis Services multidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="1eeca-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="1eeca-112">Também é possível definir alises e funções de agregação associados a tipos de contas usados pelos atributos de conta em dimensões contidas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eeca-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="1eeca-113">Os aliases permitem a seleção da terminologia específica do ramo usada pela empresa para os tipos de contas do plano de contas.</span><span class="sxs-lookup"><span data-stu-id="1eeca-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="1eeca-114">Os tipos de conta são usados pelos membros de um atributo de conta para indicar como agregar medidas em cada membro usando as funções de agregação especificadas para cada tipo de conta existente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eeca-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="1eeca-115">Para obter mais informações sobre os atributos de conta, consulte [Atributos e hierarquias de atributos](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="1eeca-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="1eeca-116">excluindo bancos de dados</span><span class="sxs-lookup"><span data-stu-id="1eeca-116">Deleting Databases</span></span>  
 <span data-ttu-id="1eeca-117">A exclusão de um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exclui o banco de dados e todos os seus cubos, dimensões e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="1eeca-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="1eeca-118">É possível excluir um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] somente no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eeca-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="1eeca-119">Para excluir um banco de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1eeca-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="1eeca-120">Conecte-se a uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1eeca-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="1eeca-121">No **Pesquisador de Objetos**, expanda o nó da instância conectada do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e verifique se o objeto a ser excluído está visível.</span><span class="sxs-lookup"><span data-stu-id="1eeca-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="1eeca-122">Clique com o botão direito do mouse no objeto a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1eeca-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="1eeca-123">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eeca-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eeca-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1eeca-124">See Also</span></span>  
 [<span data-ttu-id="1eeca-125">Documentar e gerar scripts de um banco de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1eeca-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
