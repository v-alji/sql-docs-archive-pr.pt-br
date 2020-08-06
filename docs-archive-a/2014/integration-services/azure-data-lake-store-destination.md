---
title: Destino do Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684830"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="a38c9-102">Destino do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="a38c9-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="a38c9-103">O componente **Destino do Azure Data Lake Store** permite que um pacote SSIS grave dados em um Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="a38c9-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="a38c9-104">Os formatos de arquivo com suporte são Texto, Avro e ORC.</span><span class="sxs-lookup"><span data-stu-id="a38c9-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="a38c9-105">Configure o Destino do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="a38c9-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="a38c9-106">Arraste e solte **Destino do Azure Data Lake Store** para o designer de fluxo de dados e clique duas vezes nele para ver o editor.</span><span class="sxs-lookup"><span data-stu-id="a38c9-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="a38c9-107">Para o campo **Gerenciador de conexões do Azure Data Lake Store** , especifique um Gerenciador de conexões do Azure Data Lake Store existente ou crie um novo referindo-se a um serviço do Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="a38c9-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="a38c9-108">Para o **caminho do arquivo** especifique o nome do arquivo em que você deseja gravar dados.</span><span class="sxs-lookup"><span data-stu-id="a38c9-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="a38c9-109">Se esse arquivo já existir, seu conteúdo será substituído.</span><span class="sxs-lookup"><span data-stu-id="a38c9-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="a38c9-110">Para o campo **Formato de arquivo** , especifique o formato de arquivo que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a38c9-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="a38c9-111">Se o formato de arquivo for texto, você deverá especificar o valor do **Caractere delimitador de coluna** .</span><span class="sxs-lookup"><span data-stu-id="a38c9-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="a38c9-112">Além disso, selecione **nomes de coluna na primeira linha de dados** se a primeira linha no arquivo contiver nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="a38c9-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="a38c9-113">Se o formato de arquivo for ORC, você precisa instalar o JRE da plataforma correspondente.</span><span class="sxs-lookup"><span data-stu-id="a38c9-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="a38c9-114">Depois de especificar as informações de conexão, alterne para a página **Colunas** para mapear colunas de origem para colunas de destino para o fluxo de dados do SSIS.</span><span class="sxs-lookup"><span data-stu-id="a38c9-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
