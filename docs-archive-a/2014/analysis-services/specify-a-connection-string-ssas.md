---
title: Especificar uma cadeia de conexão (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.speconnstring.f1
ms.assetid: 3f89b55b-2659-4e9f-a3ad-ab9a23b6942d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9333c239504a79184e08776acb3f1d845f06cc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683705"
---
# <a name="specify-a-connection-string-ssas"></a><span data-ttu-id="7e742-102">Especificar uma cadeia de conexão (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7e742-102">Specify a connection string (SSAS)</span></span>
  <span data-ttu-id="7e742-103">Esta página do **Assistente de Importação de Tabela** o habilita a especificar uma cadeia de conexão para estabelecer conexão com uma fonte de dados OLE DB ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="7e742-103">This page of the **Table Import Wizard** enables you to specify a connection string to connect to an OLE DB or ODBC data source.</span></span> <span data-ttu-id="7e742-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="7e742-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="7e742-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="7e742-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="7e742-106">Para obter mais informações sobre os provedores e as fontes de dados com suporte, consulte [Fontes de dados com suporte &#40;SSAS de Tabela&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7e742-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7e742-107">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="7e742-107">UI element list</span></span>  
 <span data-ttu-id="7e742-108">**Nome amigável para esta conexão**</span><span class="sxs-lookup"><span data-stu-id="7e742-108">**Friendly name for this connection**</span></span>  
 <span data-ttu-id="7e742-109">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e742-109">Type a unique name for this data source connection.</span></span> <span data-ttu-id="7e742-110">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="7e742-110">This is a required field.</span></span>  
  
 <span data-ttu-id="7e742-111">**Cadeia de conexão**</span><span class="sxs-lookup"><span data-stu-id="7e742-111">**Connection String**</span></span>  
 <span data-ttu-id="7e742-112">Digite uma cadeia de caracteres de conexão para se conectar a uma fonte de dados OLE DB ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="7e742-112">Type a connection string to connect to an OLE DB or ODBC data source.</span></span>  
  
 <span data-ttu-id="7e742-113">**Compilar**</span><span class="sxs-lookup"><span data-stu-id="7e742-113">**Build**</span></span>  
 <span data-ttu-id="7e742-114">Especifique as propriedades de uma cadeia de conexão usando a caixa de diálogo **Propriedades de Link de Dados** .</span><span class="sxs-lookup"><span data-stu-id="7e742-114">Specify the properties for a connection string by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="7e742-115">Para obter mais informações, consulte a Ajuda do Microsoft Data Link Help disponível nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7e742-115">For more information, see the Microsoft Data Link Help, which is available from that dialog box.</span></span>  
  
 <span data-ttu-id="7e742-116">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="7e742-116">**Test Connection**</span></span>  
 <span data-ttu-id="7e742-117">Tente estabelecer uma conexão com a fonte de dados usando a cadeia de caracteres de conexão especificada.</span><span class="sxs-lookup"><span data-stu-id="7e742-117">Attempt to establish a connection to the data source using the specified connection string.</span></span> <span data-ttu-id="7e742-118">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="7e742-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
