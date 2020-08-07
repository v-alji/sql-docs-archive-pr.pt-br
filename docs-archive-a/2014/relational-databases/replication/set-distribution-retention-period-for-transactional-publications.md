---
title: Definir o período de retenção de distribuição para publicações transacionais (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transaction retention periods [SQL Server replication]
- retention periods [SQL Server replication]
ms.assetid: 9a98c53a-fea5-4235-b23d-6c69587c5676
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a68f092c63e75196ab82a81d2a8ca36d13142813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583495"
---
# <a name="set-the-distribution-retention-period-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="109ea-102">Definir o período de retenção de distribuição para publicações transacionais (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="109ea-102">Set the Distribution Retention Period for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="109ea-103">Especifique o período mínimo de retenção da distribuição e o período máximo de retenção da distribuição na caixa de diálogo **Propriedades do Banco de Dados de Distribuição – \<DistributionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="109ea-103">Specify the minimum distribution retention period and maximum distribution retention period on the **Distribution Database Properties - \<DistributionDatabase>** dialog box.</span></span> <span data-ttu-id="109ea-104">Isso está disponível na página **Geral** da caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="109ea-104">This is available from the **General** page of the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="109ea-105">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [Exibir e modificar as propriedades do Distribuidor e do Publicador](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="109ea-105">For more information about accessing this dialog box, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-specify-the-distribution-retention-period"></a><span data-ttu-id="109ea-106">Para especificar o período de retenção de distribuição</span><span class="sxs-lookup"><span data-stu-id="109ea-106">To specify the distribution retention period</span></span>  
  
1.  <span data-ttu-id="109ea-107">Na página **Geral** da caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** , clique no botão de propriedades ( **...** ) do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="109ea-107">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click the properties button (**...**) for the distribution database.</span></span>  
  
2.  <span data-ttu-id="109ea-108">Para especificar o período mínimo de retenção de distribuição, insira um valor na caixa **Pelo menos** ; para especificar o período máximo de retenção de distribuição, insira um valor na caixa **Mas não mais de** .</span><span class="sxs-lookup"><span data-stu-id="109ea-108">To specify the minimum distribution retention period, enter a value in the **At least** box; to specify the maximum distribution retention period, enter a value in the **But not more than** box.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="109ea-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="109ea-109">See Also</span></span>  
 <span data-ttu-id="109ea-110">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="109ea-110">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="109ea-111">Desativação e expiração de assinatura</span><span class="sxs-lookup"><span data-stu-id="109ea-111">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
