---
title: Defina a opção do banco de dados PAGE_VERIFY como CHECKSUM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 686b9a4a-ea61-4263-9ab8-f444a3077679
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13296a976722390668b8ca6d901cf0dd080e5cc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685064"
---
# <a name="set-the-page_verify-database-option-to-checksum"></a><span data-ttu-id="be6c5-102">Definir a opção do banco de dados PAGE_VERIFY como CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="be6c5-102">Set the PAGE_VERIFY Database Option to CHECKSUM</span></span>
  <span data-ttu-id="be6c5-103">Esta regra verifica se a opção do banco de dados PAGE_VERIFY está definida como CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="be6c5-103">This rule checks whether PAGE_VERIFY database option is set to CHECKSUM.</span></span> <span data-ttu-id="be6c5-104">Quando CHECKSUM é habilitado para a opção do banco de dados PAGE_VERIFY, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calcula uma soma de verificação nos conteúdos da página inteira e armazena o valor no cabeçalho da página, quando uma página é gravada em disco.</span><span class="sxs-lookup"><span data-stu-id="be6c5-104">When CHECKSUM is enabled for the PAGE_VERIFY database option, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calculates a checksum over the contents of the whole page, and stores the value in the page header when a page is written to disk.</span></span> <span data-ttu-id="be6c5-105">Quando a página é lida pelo disco, a soma de verificação é recalculada e comparada ao valor da soma de verificação armazenado no cabeçalho da página.</span><span class="sxs-lookup"><span data-stu-id="be6c5-105">When the page is read from disk, the checksum is recomputed and compared to the checksum value that is stored in the page header.</span></span> <span data-ttu-id="be6c5-106">Isso ajuda a fornecer um alto nível de integridade de arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="be6c5-106">This helps provide a high level of data-file integrity.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="be6c5-107">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="be6c5-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="be6c5-108">Defina a opção do banco de dados PAGE_VERIFY como CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="be6c5-108">Set the PAGE_VERIFY database option to CHECKSUM.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="be6c5-109">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="be6c5-109">For More Information</span></span>  
 [<span data-ttu-id="be6c5-110">Opções ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="be6c5-110">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
