---
title: Destino de Blob do Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684272"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="60c15-102">Destino de Blob do Azure</span><span class="sxs-lookup"><span data-stu-id="60c15-102">Azure Blob Destination</span></span>
  <span data-ttu-id="60c15-103">O componente **Destino de Blob do Azure** permite que um pacote SSIS grave dados de um blob do Azure.</span><span class="sxs-lookup"><span data-stu-id="60c15-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="60c15-104">Os formatos de arquivo com suporte são: CSV e AVRO.</span><span class="sxs-lookup"><span data-stu-id="60c15-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="60c15-105">Ddrag-remova o **destino de blob do Azure** para o designer de fluxo de dados e clique duas vezes nele para ver o editor).</span><span class="sxs-lookup"><span data-stu-id="60c15-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="60c15-106">Para o campo **Gerenciador de conexões do armazenamento do Azure** , especifique um Gerenciador de Conexões do Armazenamento do Azure existente ou crie um novo referindo-se a uma Conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="60c15-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="60c15-107">Para o campo **Nome do contêiner de blobs** , especifique o nome do contêiner de blobs que contém os arquivos de origem.</span><span class="sxs-lookup"><span data-stu-id="60c15-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="60c15-108">Para o campo **Nome do Blob** , especifique o caminho para o blob.</span><span class="sxs-lookup"><span data-stu-id="60c15-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="60c15-109">Para o campo **Formato de arquivo de blob** , especifique o formato de blob que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="60c15-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="60c15-110">Se o formato de arquivo for CSV, você deverá especificar o valor do **Caractere delimitador de coluna** .</span><span class="sxs-lookup"><span data-stu-id="60c15-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="60c15-111">Além disso, selecione **nomes de coluna na primeira linha de dados** se a primeira linha no arquivo contiver nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="60c15-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="60c15-112">Depois de especificar as informações de conexão, alterne para a página **Colunas** para mapear colunas de origem para colunas de destino para o fluxo de dados do SSIS.</span><span class="sxs-lookup"><span data-stu-id="60c15-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
