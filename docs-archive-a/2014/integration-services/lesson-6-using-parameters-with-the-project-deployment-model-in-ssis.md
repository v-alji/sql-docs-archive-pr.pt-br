---
title: 'Lição 6: usando parâmetros com o modelo de implantação de projeto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571436"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="bb197-102">Lição 6: Como usar parâmetros com o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="bb197-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="bb197-103">O SQL Server 2012 apresenta um novo modelo de implantação em que você pode implantar seus projetos no servidor do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="bb197-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="bb197-104">O servidor do Integration Services permite gerenciar e executar pacotes e configurar valores de runtime para pacotes.</span><span class="sxs-lookup"><span data-stu-id="bb197-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="bb197-105">Nesta lição, você modificará o pacote criado no [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) para usar o Modelo de Implantação do Projeto.</span><span class="sxs-lookup"><span data-stu-id="bb197-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="bb197-106">Você substitui o valor de configuração com um parâmetro para especificar o local de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="bb197-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="bb197-107">Você também pode copiar o pacote concluído da Lição 5 que está incluso no tutorial.</span><span class="sxs-lookup"><span data-stu-id="bb197-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="bb197-108">Usando o Assistente de Configuração de Projeto do Integration Services, você converterá o projeto no Modelo de Implantação do Projeto e usará um parâmetro, em vez de um valor de configuração, para definir a propriedade do Diretório.</span><span class="sxs-lookup"><span data-stu-id="bb197-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="bb197-109">Esta lição abrange parcialmente as etapas que você seguirá para converter os pacotes SSIS existentes no novo Modelo de Implantação do Projeto.</span><span class="sxs-lookup"><span data-stu-id="bb197-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="bb197-110">Quando você executar o pacote novamente, o serviço Integration Services usará o parâmetro para popular o valor da variável e, por sua vez, a variável atualizará a propriedade Diretório.</span><span class="sxs-lookup"><span data-stu-id="bb197-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="bb197-111">Assim, o pacote itera pelos arquivos na nova pasta de dados especificada pelo valor de parâmetro, em vez da pasta que foi definida no arquivo de configuração do pacote.</span><span class="sxs-lookup"><span data-stu-id="bb197-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bb197-112">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="bb197-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="bb197-113">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, consulte [Considerações sobre a instalação de amostras e bancos de dados de exemplo do SQL Server](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span><span class="sxs-lookup"><span data-stu-id="bb197-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="bb197-114">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="bb197-114">Lesson Tasks</span></span>  
 <span data-ttu-id="bb197-115">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="bb197-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="bb197-116">Etapa 1: Copiar o pacote da Lição 5</span><span class="sxs-lookup"><span data-stu-id="bb197-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="bb197-117">Etapa 2: Convertendo o projeto para o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="bb197-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="bb197-118">Etapa 3: Testar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="bb197-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="bb197-119">Etapa 4: Implantar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="bb197-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="bb197-120">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="bb197-120">Start the Lesson</span></span>  
 [<span data-ttu-id="bb197-121">Etapa 1: Copiar o pacote da Lição 5</span><span class="sxs-lookup"><span data-stu-id="bb197-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
