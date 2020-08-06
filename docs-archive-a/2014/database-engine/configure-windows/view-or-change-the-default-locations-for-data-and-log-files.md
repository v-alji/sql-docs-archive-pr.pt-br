---
title: Exibir ou alterar os locais padrão de arquivos de dados e de log (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679510"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="71343-102">Exibir ou alterar os locais padrão de arquivos de log e de dados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="71343-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="71343-103">Este tópico descreve como exibir e alterar os locais padrão de novos arquivos de log e de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71343-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="71343-104">O caminho padrão é obtido do Registro.</span><span class="sxs-lookup"><span data-stu-id="71343-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="71343-105">Depois que você alterar o local, todos os novos bancos de dados criados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usarão esse local se um local diferente não for especificado.</span><span class="sxs-lookup"><span data-stu-id="71343-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="71343-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="71343-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71343-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="71343-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71343-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="71343-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="71343-109">**Para exibir ou alterar os locais padrão dos dados e do arquivos de log usando:**</span><span class="sxs-lookup"><span data-stu-id="71343-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="71343-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71343-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="71343-111">**Acompanhamento:**  [Alterando os locais padrão](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="71343-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71343-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="71343-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="71343-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="71343-113">Recommendations</span></span>  
 <span data-ttu-id="71343-114">A prática recomendada para proteger seus arquivos de dados e arquivos de log é garantir que eles sejam protegidos por ACLs (listas de controle de acesso).</span><span class="sxs-lookup"><span data-stu-id="71343-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="71343-115">As ACLs devem ser definidas no diretório raiz em que os arquivos são criados.</span><span class="sxs-lookup"><span data-stu-id="71343-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="71343-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="71343-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="71343-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="71343-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71343-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71343-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="71343-119">Para exibir ou alterar os locais padrão dos arquivos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="71343-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="71343-120">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="71343-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="71343-121">No painel esquerdo, clique na página **Configurações do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="71343-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="71343-122">Em **Locais padrão de banco de dados**, exiba os locais atuais padrão dos novos arquivos de dados e novos arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="71343-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="71343-123">Para alterar um local padrão, digite um novo nome de caminho padrão no campo **Dados** ou **Log** ou clique no botão Procurar para localizar e selecionar um nome de caminho.</span><span class="sxs-lookup"><span data-stu-id="71343-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="71343-124">Acompanhamento: depois de alterar os locais padrão</span><span class="sxs-lookup"><span data-stu-id="71343-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="71343-125">Você deve parar e iniciar o serviço do SQL Server para concluir a alteração.</span><span class="sxs-lookup"><span data-stu-id="71343-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71343-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71343-126">See Also</span></span>  
 <span data-ttu-id="71343-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71343-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="71343-128">Criar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="71343-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
