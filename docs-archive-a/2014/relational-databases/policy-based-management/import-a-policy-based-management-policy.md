---
title: Importar uma política do Gerenciamento Baseado em Políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569984"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="a4e42-102">Importar política de Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="a4e42-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="a4e42-103">Este tópico descreve como importar uma instância de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4e42-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a4e42-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a4e42-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4e42-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a4e42-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4e42-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a4e42-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a4e42-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="a4e42-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a4e42-108">**Para importar uma instância de política, usando:**</span><span class="sxs-lookup"><span data-stu-id="a4e42-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="a4e42-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4e42-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4e42-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a4e42-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a4e42-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a4e42-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a4e42-112">transporta políticas que podem ser usadas para monitorar uma instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4e42-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a4e42-113">Por padrão, essas políticas não são instaladas no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]; no entanto, elas podem ser importadas do local de instalação padrão C:\Arquivos de Programas\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="a4e42-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4e42-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="a4e42-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4e42-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="a4e42-115">Permissions</span></span>  
 <span data-ttu-id="a4e42-116">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="a4e42-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4e42-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4e42-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="a4e42-118">Para importar uma instância de política</span><span class="sxs-lookup"><span data-stu-id="a4e42-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="a4e42-119">No painel **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor em que a instância de política recém-importada residirá.</span><span class="sxs-lookup"><span data-stu-id="a4e42-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="a4e42-120">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="a4e42-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="a4e42-121">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="a4e42-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="a4e42-122">Clique com o botão direito do mouse na pasta **Políticas** e selecione **Importar Política**.</span><span class="sxs-lookup"><span data-stu-id="a4e42-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="a4e42-123">Na caixa de diálogo **Importar** , digite o caminho e o nome do arquivo ou use o botão Procurar ( **...** ) para localizar o arquivo XML que contém a política e selecione o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a4e42-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="a4e42-124">Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Importar** , consulte [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a4e42-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="a4e42-125">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4e42-125">When finished, click **OK**.</span></span>  
  
  
