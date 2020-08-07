---
title: Banco de dados do Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575177"
---
# <a name="master-data-services-database"></a><span data-ttu-id="140b8-102">Banco de dados do Master Data Services</span><span class="sxs-lookup"><span data-stu-id="140b8-102">Master Data Services Database</span></span>
  <span data-ttu-id="140b8-103">O banco de dados contém todas as informações do sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="140b8-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="140b8-104">Ele é fundamental para uma implantação do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="140b8-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="140b8-105">O banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="140b8-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="140b8-106">Armazena as configurações, os objetos de banco de dados e os dados necessários ao sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="140b8-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="140b8-107">Contém tabelas de preparo que são usadas para processar dados de sistemas de origem.</span><span class="sxs-lookup"><span data-stu-id="140b8-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="140b8-108">Fornece um esquema e objetos de banco de dados para armazenar dados mestre de sistemas de origem.</span><span class="sxs-lookup"><span data-stu-id="140b8-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="140b8-109">Oferece suporte à funcionalidade de controle de versão, inclusive validação de regra de negócio e notificações por email.</span><span class="sxs-lookup"><span data-stu-id="140b8-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="140b8-110">Fornece exibições para sistemas de assinatura que precisam recuperar dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="140b8-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="140b8-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="140b8-111">In This Section</span></span>  
  
-   [<span data-ttu-id="140b8-112">Tabela de preparo de membros folha &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="140b8-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="140b8-113">Tabela de preparo de membros consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="140b8-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="140b8-114">Tabela de preparo de relações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="140b8-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="140b8-115">Erros de processo de preparo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="140b8-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="140b8-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="140b8-116">See Also</span></span>  
 <span data-ttu-id="140b8-117">[Criar um banco de dados Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="140b8-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="140b8-118">[&#40;de segurança de objeto de banco de dados Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="140b8-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="140b8-119">Logons, usuários e funções de banco de dados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="140b8-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
