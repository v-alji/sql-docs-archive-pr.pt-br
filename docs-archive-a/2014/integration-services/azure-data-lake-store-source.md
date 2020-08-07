---
title: Origem do Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575296"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="c266c-102">Fonte do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="c266c-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="c266c-103">O componente de **Fonte do Azure Data Lake Store** permite que um pacote SSIS leia dados de um Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c266c-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="c266c-104">Os formatos de arquivo com suporte são texto e Avro.</span><span class="sxs-lookup"><span data-stu-id="c266c-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="c266c-105">Configure a Fonte do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="c266c-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="c266c-106">Para ver o editor da Fonte do Azure Data Lake Store, arraste e solte **Fonte do Azure Data Lake Store** no designer de fluxo de dados e clique duas vezes nela para abrir o editor.</span><span class="sxs-lookup"><span data-stu-id="c266c-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="c266c-107">Para o campo **Gerenciador de conexões do Azure Data Lake Store** , especifique um Gerenciador de conexões do Azure Data Lake Store existente ou crie um novo referindo-se a um serviço do Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c266c-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="c266c-108">Para o campo **caminho do arquivo** especifique o caminho do arquivo do arquivo de origem no armazenamento do Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c266c-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="c266c-109">Para o campo **formato de arquivo** especifique o formato de arquivo do arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="c266c-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="c266c-110">Se o formato de arquivo for texto, você deverá especificar o valor do **Caractere delimitador de coluna** .</span><span class="sxs-lookup"><span data-stu-id="c266c-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="c266c-111">Além disso, selecione **Nomes de coluna na primeira linha de dados** se a primeira linha no arquivo contiver nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="c266c-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="c266c-112">Depois de especificar as informações de conexão, alterne para a página **Colunas** para mapear colunas de origem para colunas de destino para o fluxo de dados do SSIS.</span><span class="sxs-lookup"><span data-stu-id="c266c-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
