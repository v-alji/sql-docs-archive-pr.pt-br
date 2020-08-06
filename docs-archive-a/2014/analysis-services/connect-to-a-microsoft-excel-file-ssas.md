---
title: Conectar-se a um arquivo do Microsoft Excel (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571024"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="38437-102">Conectar a um arquivo do Microsoft Excel (SSAS)</span><span class="sxs-lookup"><span data-stu-id="38437-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="38437-103">Esta página do **Assistente de Importação de Tabela** o habilita a conectar um arquivo do Microsoft Excel armazenado no computador local.</span><span class="sxs-lookup"><span data-stu-id="38437-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="38437-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="38437-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="38437-105">Para conectar um arquivo do Microsoft Excel, você deve ter o provedor ACE apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="38437-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="38437-106">Para obter mais informações, consulte [Fontes de dados com suporte &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="38437-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38437-107">As credenciais do usuário atual são usadas na seleção de um arquivo nesta página.</span><span class="sxs-lookup"><span data-stu-id="38437-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="38437-108">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="38437-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="38437-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="38437-109">UI element list</span></span>  
 <span data-ttu-id="38437-110">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="38437-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="38437-111">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="38437-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="38437-112">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="38437-112">This is a required field.</span></span>  
  
 <span data-ttu-id="38437-113">**Caminho do arquivo do Excel**</span><span class="sxs-lookup"><span data-stu-id="38437-113">**Excel File Path**</span></span>  
 <span data-ttu-id="38437-114">Especifique um caminho completo para o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="38437-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="38437-115">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="38437-115">**Browse**</span></span>  
 <span data-ttu-id="38437-116">Navegue até um local onde um arquivo do Excel está disponível.</span><span class="sxs-lookup"><span data-stu-id="38437-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="38437-117">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="38437-117">**Advanced**</span></span>  
 <span data-ttu-id="38437-118">Defina propriedades de conexão adicionais usando a caixa de diálogo **definir propriedades avançadas** .</span><span class="sxs-lookup"><span data-stu-id="38437-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="38437-119">**Usar primeira linha como cabeçalhos de coluna**</span><span class="sxs-lookup"><span data-stu-id="38437-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="38437-120">Especifique se deseja usar a primeira linha de dados como o cabeçalho de coluna da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="38437-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="38437-121">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="38437-121">**Test Connection**</span></span>  
 <span data-ttu-id="38437-122">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="38437-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="38437-123">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="38437-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
