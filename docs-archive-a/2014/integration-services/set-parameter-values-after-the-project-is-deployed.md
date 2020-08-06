---
title: Definir valores de parâmetro depois que o projeto for implantado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685842"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="b5f27-102">Definir valores de parâmetros depois que o projeto foi implantado</span><span class="sxs-lookup"><span data-stu-id="b5f27-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="b5f27-103">O Assistente de Implantação permite definir valores de parâmetros padrão de servidor ao implantar seu projeto no catálogo.</span><span class="sxs-lookup"><span data-stu-id="b5f27-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="b5f27-104">Depois que seu projeto estiver no catálogo, você pode usar o Pesquisador de Objetos do SQL Server Management Studio (SSMS) ou o Transact-SQL para definir valores padrão de servidor.</span><span class="sxs-lookup"><span data-stu-id="b5f27-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="b5f27-105">Para definir padrões de servidor com Pesquisador de Objetos do SSMS:</span><span class="sxs-lookup"><span data-stu-id="b5f27-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="b5f27-106">Selecione e clique com o botão direito do mouse no projeto sob o nó **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="b5f27-107">Clique em **Propriedades** para abrir janela da caixa de diálogo **Propriedades do Projeto**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="b5f27-108">Abra a página de parâmetros com um clique em **Parâmetros** sob **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="b5f27-109">Selecione o parâmetro desejado na lista **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="b5f27-110">Observação: a coluna **Contêiner** ajuda a distinguir os parâmetros de projeto dos parâmetros de pacote.</span><span class="sxs-lookup"><span data-stu-id="b5f27-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="b5f27-111">Na coluna **Valor**, especifique o valor do parâmetro padrão de servidor desejado.</span><span class="sxs-lookup"><span data-stu-id="b5f27-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="b5f27-112">Para definir padrões de servidor com Transact-SQL, use o procedimento armazenado [catalog.set_object_parameter_value &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="b5f27-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="b5f27-113">Para exibir os padrões atuais de servidor, consulte a exibição [catalog.object_parameters &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="b5f27-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="b5f27-114">Para apagar um valor padrão de servidor, use o procedimento armazenado [catalog.clear_object_parameter_value &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="b5f27-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f27-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5f27-115">See Also</span></span>  
 [<span data-ttu-id="b5f27-116">Integration Services parâmetros&#41; &#40;SSIS</span><span class="sxs-lookup"><span data-stu-id="b5f27-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
