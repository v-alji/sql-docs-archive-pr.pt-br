---
title: Propriedades de distribuição | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569926"
---
# <a name="distribution-database"></a><span data-ttu-id="597a3-102">Banco de dados de distribuição</span><span class="sxs-lookup"><span data-stu-id="597a3-102">Distribution Database</span></span>
  <span data-ttu-id="597a3-103">O banco de dados de distribuição armazena metadados e dados de histórico para todos os tipos de replicação e transações para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="597a3-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="597a3-104">Em muitos casos, um único banco de dados de distribuição é suficiente.</span><span class="sxs-lookup"><span data-stu-id="597a3-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="597a3-105">Porém, se vários Publicadores usarem um único Distribuidor, considere criar um banco de dados de distribuição para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="597a3-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="597a3-106">Fazer isso assegura que os dados que fluem por cada banco de dados de distribuição são distintos.</span><span class="sxs-lookup"><span data-stu-id="597a3-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="597a3-107">Você pode especificar um banco de dados de distribuição para o Distribuidor usando o Assistente para Configurar a Distribuição.</span><span class="sxs-lookup"><span data-stu-id="597a3-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="597a3-108">Se necessário, especifique bancos de dados de distribuição adicionais na caixa de diálogo **Propriedades do Distribuidor** .</span><span class="sxs-lookup"><span data-stu-id="597a3-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="597a3-109">Opções</span><span class="sxs-lookup"><span data-stu-id="597a3-109">Options</span></span>  
 <span data-ttu-id="597a3-110">**Nome do Banco de Dados de Distribuição**</span><span class="sxs-lookup"><span data-stu-id="597a3-110">**Distribution database name**</span></span>  
 <span data-ttu-id="597a3-111">Insira um nome para o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="597a3-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="597a3-112">O nome padrão para o banco de dados de distribuição é “distribuição”.</span><span class="sxs-lookup"><span data-stu-id="597a3-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="597a3-113">Se você especificar um nome, o nome poderá ter no máximo 128 caracteres, deve ser exclusivo em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], e deve estar em conformidade com as regras para identificadores.</span><span class="sxs-lookup"><span data-stu-id="597a3-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="597a3-114">Para obter mais informações, consulte [Database Identifiers](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="597a3-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="597a3-115">**Pasta para o arquivo de banco de dados de distribuição** e **Pasta para o arquivo de log de banco de dados de distribuição**</span><span class="sxs-lookup"><span data-stu-id="597a3-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="597a3-116">Insira o caminho para o banco de dados de distribuição e arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="597a3-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="597a3-117">Os caminhos devem se referir aos discos locais do Distribuidor e começar com uma letra de unidade e dois pontos (por exemplo, C:).</span><span class="sxs-lookup"><span data-stu-id="597a3-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="597a3-118">Letras de unidades e caminhos de rede mapeados não são válidos.</span><span class="sxs-lookup"><span data-stu-id="597a3-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="597a3-119">Você pode diminuir o tempo de gravação das transações e aprimorar o desempenho da replicação colocando o log do banco de dados de distribuição em uma unidade de disco separada do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="597a3-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597a3-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="597a3-120">See Also</span></span>  
 <span data-ttu-id="597a3-121">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="597a3-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="597a3-122">[Configurar a publicação e a distribuição](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="597a3-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="597a3-123">Exibir e modificar propriedades de Publicador e Distribuidor</span><span class="sxs-lookup"><span data-stu-id="597a3-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
