---
title: Tutoriais de gerenciamento de informações da empresa | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8745dc80-193d-4de0-9f17-ba648ab1e81c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8cde162479645ab13a6ae000cc46e42e3c10e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576086"
---
# <a name="enterprise-information-management-tutorials"></a><span data-ttu-id="952e8-102">Tutoriais de Gerenciamento de Informações da Empresa</span><span class="sxs-lookup"><span data-stu-id="952e8-102">Enterprise Information Management Tutorials</span></span>
  <span data-ttu-id="952e8-103">Esta seção contém tutoriais para gerenciar as informações em uma empresa usando as tecnologias de EIM (Gerenciamento de Informações da Empresa) incluídas no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="952e8-103">This section contains tutorials for managing information in an enterprise by using Enterprise Information Management (EIM) technologies that are included in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span> <span data-ttu-id="952e8-104">O EIM (Gerenciamento de Informações da Empresa) fornece um portfólio de soluções que permitem que as organizações confiem na credibilidade e na consistência de seus dados para que possam tomar decisões comerciais críticas.</span><span class="sxs-lookup"><span data-stu-id="952e8-104">Enterprise Integration Management (EIM) provides a portfolio of solutions that enable organizations to trust the credibility and consistency of their data so they can make critical business decisions.</span></span> <span data-ttu-id="952e8-105">O [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] tem as tecnologias a seguir que o ajudam a implementar soluções de EIM na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="952e8-105">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] has the following technologies that help you implement EIM solutions in your enterprise.</span></span>  
  
-   <span data-ttu-id="952e8-106">SQL Server Integration Services (SSIS).</span><span class="sxs-lookup"><span data-stu-id="952e8-106">SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="952e8-107">O SSIS fornece uma plataforma sofisticada e extensível para a integração de dados de várias fontes em uma solução de extração, transformação e carregamento (ETL) abrangente que oferece suporte a fluxos de trabalho comerciais, data warehouse ou gerenciamento de dados mestres.</span><span class="sxs-lookup"><span data-stu-id="952e8-107">SSIS provides a powerful, extensible platform for integrating data from various sources in a comprehensive extract, transform, and load (ETL) solution that supports business workflows, a data warehouse, or master data management.</span></span>  
  
-   <span data-ttu-id="952e8-108">SQL Server Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="952e8-108">SQL Server Data Quality Services (DQS).</span></span> <span data-ttu-id="952e8-109">O DQS permite a limpeza, a correspondência, a padronização e o enriquecimento dos dados; portanto, é possível enviar informações confiáveis para business intelligence, data warehouse e cargas de trabalho de processamento de transações.</span><span class="sxs-lookup"><span data-stu-id="952e8-109">DQS enables you to cleanse, match, standardize, and enrich data, so you can deliver trusted information for business intelligence, a data warehouse, and transaction processing workloads.</span></span>  
  
-   <span data-ttu-id="952e8-110">SQL Server Master Data Services (MDS).</span><span class="sxs-lookup"><span data-stu-id="952e8-110">SQL Server Master Data Services (MDS).</span></span> <span data-ttu-id="952e8-111">O MDS fornece um hub de dados central que assegura a constante integridade das informações e consistência dos dados entre diferentes aplicativos.</span><span class="sxs-lookup"><span data-stu-id="952e8-111">MDS provides a central data hub that ensures that the integrity of information and consistency of data is constant across different applications.</span></span>  
  
 [<span data-ttu-id="952e8-112">O gerenciamento de informações corporativas usando o SSIS, o MDS e o DQS juntos &#91;tutorial&#93;</span><span class="sxs-lookup"><span data-stu-id="952e8-112">Enterprise Information Management using SSIS, MDS, and DQS Together &#91;Tutorial&#93;</span></span>](../../2014/tutorials/enterprise-information-management-using-ssis-mds-and-dqs-together-[tutorial].md)  
 <span data-ttu-id="952e8-113">Neste tutorial, você aprenderá a usar o SSIS, o MDS e o DQS em conjunto para implementar um exemplo de solução de Gerenciamento de informações da empresa (EIM).</span><span class="sxs-lookup"><span data-stu-id="952e8-113">In this tutorial, you learn how to use SSIS, MDS, and DQS together to implement a sample Enterprise Information Management (EIM) solution.</span></span> <span data-ttu-id="952e8-114">Primeiro, use o DQS para criar uma base de dados de conhecimento com informações sobre os dados do fornecedor (metadados), limpar os dados em um arquivo do Excel usando a base de dados de conhecimento e faça a correspondência dos dados para identificar e remover duplicatas.</span><span class="sxs-lookup"><span data-stu-id="952e8-114">First, you use DQS to create a knowledgebase with the knowledge about the supplier data (metadata), cleanse the data in an Excel file against the knowledge base, and match the data to identify and remove duplicates in the data.</span></span> <span data-ttu-id="952e8-115">Em seguida, use o Suplemento MDS para Excel a fim de carregar os dados limpos e correspondentes no MDS.</span><span class="sxs-lookup"><span data-stu-id="952e8-115">Next, you use the MDS Add-in for Excel to upload the cleansed and matched data to MDS.</span></span> <span data-ttu-id="952e8-116">Depois, automatize todo o processo usando uma solução SSIS.</span><span class="sxs-lookup"><span data-stu-id="952e8-116">Then, you automate the whole process by using an SSIS solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952e8-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="952e8-117">See Also</span></span>  
 [<span data-ttu-id="952e8-118">Gerenciamento de informações da empresa-Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="952e8-118">Enterprise Information Management - Microsoft SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=270871)  
  
  
