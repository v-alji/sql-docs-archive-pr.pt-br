---
title: Conectar ao Servidor (Oracle), Propriedades da Conexão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569379"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="c9363-102">Conectar ao Servidor (Oracle), Propriedades da Conexão</span><span class="sxs-lookup"><span data-stu-id="c9363-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="c9363-103">Use a guia **Propriedades de Conexão** da caixa de diálogo **Conectar ao Servidor** para especificar uma opção de publicação **Gateway** ou **Completa**.</span><span class="sxs-lookup"><span data-stu-id="c9363-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="c9363-104">Depois que um Publicador é identificado, essa opção não pode ser alterada sem descartar e reconfigurar o Publicador.</span><span class="sxs-lookup"><span data-stu-id="c9363-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="c9363-105">Para obter mais informações, consulte [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md) (Configurar um publicador do Oracle).</span><span class="sxs-lookup"><span data-stu-id="c9363-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9363-106">Opções</span><span class="sxs-lookup"><span data-stu-id="c9363-106">Options</span></span>  
 <span data-ttu-id="c9363-107">**Tipo de publicador**</span><span class="sxs-lookup"><span data-stu-id="c9363-107">**Publisher type**</span></span>  
 <span data-ttu-id="c9363-108">Selecione **Gateway** ou **Completa**.</span><span class="sxs-lookup"><span data-stu-id="c9363-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="c9363-109">A opção **Completa** é projetada para fornecer publicações transacionais e de instantâneo com o conjunto completo de recursos com suporte para publicações Oracle.</span><span class="sxs-lookup"><span data-stu-id="c9363-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="c9363-110">A opção **Gateway** fornece otimizações de projeto específicas para aprimorar o desempenho de casos em que a replicação serve como um gateway entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="c9363-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="c9363-111">A opção **Gateway** não poderá ser usada se você planejar publicar a mesma tabela em várias publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="c9363-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="c9363-112">Uma tabela pode aparecer no máximo em uma publicação transacional e em qualquer número de publicações de instantâneo se você selecionar **Gateway**.</span><span class="sxs-lookup"><span data-stu-id="c9363-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="c9363-113">**Tempo Limite**</span><span class="sxs-lookup"><span data-stu-id="c9363-113">**Timeouts**</span></span>  
 <span data-ttu-id="c9363-114">Especifique por quanto tempo o Distribuidor do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve tentar se conectar ao Publicador Oracle antes da ocorrência de um erro de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="c9363-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9363-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9363-115">See Also</span></span>  
 <span data-ttu-id="c9363-116">[Glossário de termos para publicações Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="c9363-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="c9363-117">Ajuste de desempenho para Publicadores Oracle</span><span class="sxs-lookup"><span data-stu-id="c9363-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
