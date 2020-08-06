---
title: Banco de dados de publicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569352"
---
# <a name="publication-database"></a><span data-ttu-id="b9450-102">Banco de dados de publicação</span><span class="sxs-lookup"><span data-stu-id="b9450-102">Publication Database</span></span>
  <span data-ttu-id="b9450-103">O banco de dados de publicação é o banco de dados no publicador que é a fonte dos dados e objetos de banco de dados a serem replicados.</span><span class="sxs-lookup"><span data-stu-id="b9450-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="b9450-104">Cada banco de dados de publicação usado na replicação deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="b9450-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="b9450-105">O banco de dados está habilitado quando um membro da função de servidor fixa **sysadmin** :</span><span class="sxs-lookup"><span data-stu-id="b9450-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="b9450-106">Cria uma publicação naquele banco de dados usando o Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="b9450-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="b9450-107">Seleciona o banco de dados na caixa de diálogo **Propriedades do Publicador** .</span><span class="sxs-lookup"><span data-stu-id="b9450-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="b9450-108">Executa **sp_replicationdboption** e define a opção **publish** (para publicações transacionais ou de instantâneo) ou **merge publish** (para publicações de mesclagem) como **True**.</span><span class="sxs-lookup"><span data-stu-id="b9450-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9450-109">Opções</span><span class="sxs-lookup"><span data-stu-id="b9450-109">Options</span></span>  
 <span data-ttu-id="b9450-110">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="b9450-110">**Databases**</span></span>  
 <span data-ttu-id="b9450-111">Selecione o nome do banco de dados que contém os dados e os objetos de banco de dados que você quer publicar.</span><span class="sxs-lookup"><span data-stu-id="b9450-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9450-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9450-112">See Also</span></span>  
 <span data-ttu-id="b9450-113">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="b9450-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="b9450-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="b9450-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="b9450-115">[Exibir e modificar propriedades de Publicador e Distribuidor](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b9450-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="b9450-116">sp_replicationdboption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9450-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
