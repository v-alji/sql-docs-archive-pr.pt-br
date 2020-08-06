---
title: Conectar-se a um repositório do MDS (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680013"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="03a42-102">Conectar-se a um repositório do MDS (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="03a42-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="03a42-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], você deve se conectar a um repositório do MDS antes de poder carregar ou publicar dados.</span><span class="sxs-lookup"><span data-stu-id="03a42-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="03a42-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="03a42-104">Prerequisites</span></span>  
 <span data-ttu-id="03a42-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="03a42-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="03a42-106">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="03a42-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="03a42-107">Para conectar-se a um repositório do MDS</span><span class="sxs-lookup"><span data-stu-id="03a42-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="03a42-108">No MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], na guia **Dados Mestre** , no grupo **Conectar e Carregar** , clique na seta sob o botão **Conectar** e clique em **Gerenciar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="03a42-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="03a42-109">Na caixa de diálogo **Gerenciar Conexões** , na seção **Nova uma conexão** , clique em **Criar uma nova conexão**.</span><span class="sxs-lookup"><span data-stu-id="03a42-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="03a42-110">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="03a42-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="03a42-111">Na caixa de diálogo **Adicionar Nova Conexão** , no campo **Descrição** , digite uma descrição para a conexão.</span><span class="sxs-lookup"><span data-stu-id="03a42-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="03a42-112">Essa conexão será exibida quando você clicar na seta sob o botão **Conectar** da barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="03a42-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="03a42-113">Na caixa **Endereço do servidor MDS**, digite a URL do aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], por exemplo, http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="03a42-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03a42-114">Verifique se você usa o nome do computador; não use "localhost".</span><span class="sxs-lookup"><span data-stu-id="03a42-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="03a42-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a42-115">Click **OK**.</span></span> <span data-ttu-id="03a42-116">O nome será exibido na seção **Conexões Existentes** .</span><span class="sxs-lookup"><span data-stu-id="03a42-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="03a42-117">Opcionalmente, clique em **Testar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="03a42-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="03a42-118">Uma caixa de diálogo de confirmação ou de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="03a42-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="03a42-119">Clique em **OK** para fechá-la.</span><span class="sxs-lookup"><span data-stu-id="03a42-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="03a42-120">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="03a42-120">Click **Connect**.</span></span> <span data-ttu-id="03a42-121">O painel **Master Data Services** será exibido.</span><span class="sxs-lookup"><span data-stu-id="03a42-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="03a42-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="03a42-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="03a42-123">Carregar dados do MDS no Excel</span><span class="sxs-lookup"><span data-stu-id="03a42-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="03a42-124">Filtrar dados antes de carregar &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="03a42-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="03a42-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="03a42-125">See Also</span></span>  
 [<span data-ttu-id="03a42-126">Conexões &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="03a42-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
