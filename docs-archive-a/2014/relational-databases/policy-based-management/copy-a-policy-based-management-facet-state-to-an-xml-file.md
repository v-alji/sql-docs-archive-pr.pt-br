---
title: Copiar um estado de faceta do gerenciamento baseado em políticas para um arquivo XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680375"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="60e4b-102">Copiar um estado de faceta do Gerenciamento Baseado em Políticas para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="60e4b-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="60e4b-103">Este tópico descreve como copiar o estado de uma faceta de Gerenciamento Baseado em Política para um arquivo XML no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60e4b-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="60e4b-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="60e4b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60e4b-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="60e4b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60e4b-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="60e4b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60e4b-107">**Para copiar um estado de faceta para um arquivo XML, usando:**</span><span class="sxs-lookup"><span data-stu-id="60e4b-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="60e4b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60e4b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60e4b-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60e4b-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60e4b-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="60e4b-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60e4b-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="60e4b-111">Permissions</span></span>  
 <span data-ttu-id="60e4b-112">Os procedimentos deste tópico exigem a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="60e4b-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60e4b-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60e4b-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="60e4b-114">Para copiar um estado de faceta para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="60e4b-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="60e4b-115">No Pesquisador de Objetos, clique com o botão direito do mouse em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um objeto de instância, banco de dados ou objeto de banco de dados e clique em **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="60e4b-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="60e4b-116">Na caixa de diálogo **Exibir Facetas -**_nome_do_objeto_, clique em **Exportar Estado Atual como Política**.</span><span class="sxs-lookup"><span data-stu-id="60e4b-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="60e4b-117">Na caixa de diálogo **Exportar como Política** , digite o caminho e o nome do arquivo ou use o botão Procurar (**...**) para localizar o arquivo e digite o nome do arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="60e4b-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="60e4b-118">Para obter mais informações sobre as opções disponíveis nesta caixa de diálogo, consulte [Export As Policy Dialog Box](export-as-policy-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="60e4b-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="60e4b-119">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60e4b-119">When finished, click **OK**.</span></span>  
  
  
