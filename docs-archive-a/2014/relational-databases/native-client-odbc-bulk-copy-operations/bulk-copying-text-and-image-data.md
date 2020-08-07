---
title: Cópia de dados de texto e imagem em massa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583571"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="4a70b-102">Copiando em massa dados de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="4a70b-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="4a70b-103">Os valores de **texto**grande, **ntext**e **Image** são copiados em massa usando a função [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) .</span><span class="sxs-lookup"><span data-stu-id="4a70b-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="4a70b-104">Você codifica [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) para a coluna **Text**, **ntext**ou **Image** com um ponteiro *pData* definido como NULL, indicando que os dados serão fornecidos com **bcp_moretext**.</span><span class="sxs-lookup"><span data-stu-id="4a70b-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="4a70b-105">É importante especificar o comprimento exato dos dados fornecidos para cada coluna **Text**, **ntext**ou **Image** em cada linha copiada em massa.</span><span class="sxs-lookup"><span data-stu-id="4a70b-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="4a70b-106">Se o comprimento dos dados de uma coluna for diferente do comprimento da coluna especificado em [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) para definir o comprimento como o valor adequado.</span><span class="sxs-lookup"><span data-stu-id="4a70b-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="4a70b-107">Um [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) envia todos os dados que não são de**texto**, não**ntextos**e não de**imagem** ; em seguida, você chama **bcp_moretext** para enviar os dados **Text**, **ntext**ou **Image** em unidades separadas.</span><span class="sxs-lookup"><span data-stu-id="4a70b-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="4a70b-108">As funções de cópia em massa determinam que todos os dados foram enviados para a coluna **Text**, **ntext**ou **Image** atual quando a soma dos comprimentos de dados enviados por meio de **bcp_moretext** é igual ao comprimento especificado no **bcp_collen** ou **bcp_bind**mais recente.</span><span class="sxs-lookup"><span data-stu-id="4a70b-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="4a70b-109">**bcp_moretext** não tem nenhum parâmetro para identificar uma coluna.</span><span class="sxs-lookup"><span data-stu-id="4a70b-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="4a70b-110">Quando há várias colunas **Text**, **ntext**ou **image** em uma linha, **bcp_moretext** opera nas colunas **Text**, **ntext**ou **Image** , começando com a coluna que tem o número ordinal mais baixo e prosseguindo para a coluna com o número ordinal mais alto.</span><span class="sxs-lookup"><span data-stu-id="4a70b-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="4a70b-111">**bcp_moretext** vai de uma coluna para a próxima quando a soma dos comprimentos de dados enviados for igual ao comprimento especificado no **bcp_collen** ou **bcp_bind** mais recente da coluna atual.</span><span class="sxs-lookup"><span data-stu-id="4a70b-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a70b-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a70b-112">See Also</span></span>  
 [<span data-ttu-id="4a70b-113">Executando operações de cópia em massa &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="4a70b-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
