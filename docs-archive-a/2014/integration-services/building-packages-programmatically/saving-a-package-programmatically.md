---
title: Salvar um pacote programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572145"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="35d82-102">Salvando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="35d82-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="35d82-103">Depois de criar um pacote novo programaticamente, ou modificar um existente, em geral você deseja salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="35d82-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="35d82-104">Todos os métodos usados nesse tópico para salvar pacotes exigem uma referência ao assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="35d82-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="35d82-105">Após adicionar a referência em um novo projeto, importe o namespace <xref:Microsoft.SqlServer.Dts.Runtime> com uma instrução `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="35d82-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="35d82-106">Salvando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="35d82-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="35d82-107">Para salvar um pacote programaticamente, chame um dos seguintes métodos da classe [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do <xref:Microsoft.SqlServer.Dts.Runtime.Application>:</span><span class="sxs-lookup"><span data-stu-id="35d82-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="35d82-108">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="35d82-108">Storage Location</span></span>|<span data-ttu-id="35d82-109">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="35d82-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="35d82-110">Arquivo</span><span class="sxs-lookup"><span data-stu-id="35d82-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="35d82-111">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="35d82-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="35d82-112">ou</span><span class="sxs-lookup"><span data-stu-id="35d82-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="35d82-113">Os métodos da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabalhar com o Repositório de Pacotes SSIS só dão suporte a "." ou ao nome do servidor local.</span><span class="sxs-lookup"><span data-stu-id="35d82-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="35d82-114">Você não pode usar"(local)" ou "localhost".</span><span class="sxs-lookup"><span data-stu-id="35d82-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="35d82-115">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="35d82-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="35d82-116">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="35d82-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="35d82-117">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="35d82-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="35d82-118">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="35d82-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d82-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35d82-119">See Also</span></span>  
 [<span data-ttu-id="35d82-120">Salvar pacotes</span><span class="sxs-lookup"><span data-stu-id="35d82-120">Save Packages</span></span>](../save-packages.md)  
  
  
