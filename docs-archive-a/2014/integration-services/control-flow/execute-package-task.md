---
title: Tarefa Executar Pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.f1
helpviewer_keywords:
- Execution Package task [Integration Services]
- child packages
- parent packages [Integration Services]
ms.assetid: 042d4ec0-0668-401c-bb3a-a25fe2602eac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f02594d67ad704885de1456651f5d086687ffd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574215"
---
# <a name="execute-package-task"></a><span data-ttu-id="01c3e-102">Tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="01c3e-102">Execute Package Task</span></span>
  <span data-ttu-id="01c3e-103">A tarefa Executar Pacote estende os recursos empresariais do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ao permitir que pacotes executem outros pacotes como parte de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-103">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="01c3e-104">Você pode usar a tarefa Executar Pacote para os seguintes propósitos:</span><span class="sxs-lookup"><span data-stu-id="01c3e-104">You can use the Execute Package task for the following purposes:</span></span>  
  
-   <span data-ttu-id="01c3e-105">Decompor fluxo de trabalho de pacote complexo.</span><span class="sxs-lookup"><span data-stu-id="01c3e-105">Breaking down complex package workflow.</span></span> <span data-ttu-id="01c3e-106">Essa tarefa permite decompor o fluxo de trabalho em vários pacotes, que são mais fáceis de ler, testar e manter.</span><span class="sxs-lookup"><span data-stu-id="01c3e-106">This task lets you break down workflow into multiple packages, which are easier to read, test, and maintain.</span></span> <span data-ttu-id="01c3e-107">Por exemplo, se estiver carregando dados em um esquema de estrela, você poderá criar um pacote separado para preencher cada dimensão e a tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="01c3e-107">For example, if you are loading data into a star schema, you can build a separate package to populate each dimension and the fact table.</span></span>  
  
-   <span data-ttu-id="01c3e-108">Reutilizando partes de pacotes.</span><span class="sxs-lookup"><span data-stu-id="01c3e-108">Reusing parts of packages.</span></span> <span data-ttu-id="01c3e-109">Outros pacotes podem reutilizar partes de um fluxo de trabalho de pacote.</span><span class="sxs-lookup"><span data-stu-id="01c3e-109">Other packages can reuse parts of a package workflow.</span></span> <span data-ttu-id="01c3e-110">Por exemplo, você pode criar um módulo de extração de dados que pode ser chamado de diferentes pacotes.</span><span class="sxs-lookup"><span data-stu-id="01c3e-110">For example, you can build a data extraction module that can be called from different packages.</span></span> <span data-ttu-id="01c3e-111">Cada pacote que chama o módulo de extração pode realizar diferentes anulações de dados, filtragem ou operações de agregação.</span><span class="sxs-lookup"><span data-stu-id="01c3e-111">Each package that calls the extraction module can perform different data scrubbing, filtering, or aggregation operations.</span></span>  
  
-   <span data-ttu-id="01c3e-112">Agrupando unidades de trabalho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-112">Grouping work units.</span></span> <span data-ttu-id="01c3e-113">Unidades de trabalho podem ser encapsuladas em pacotes separados e unidas como componentes transacionais ao fluxo de trabalho de um pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-113">Units of work can be encapsulated into separate packages and joined as transactional components to the workflow of a parent package.</span></span> <span data-ttu-id="01c3e-114">Por exemplo, o pacote pai executa os pacotes acessório e, com base no sucesso ou fracasso dos pacotes acessório, o pacote pai confirma ou reverte a transação.</span><span class="sxs-lookup"><span data-stu-id="01c3e-114">For example, the parent package runs the accessory packages, and based on the success or failure of the accessory packages, the parent package either commits or rolls back the transaction.</span></span>  
  
-   <span data-ttu-id="01c3e-115">Controlando segurança de pacote.</span><span class="sxs-lookup"><span data-stu-id="01c3e-115">Controlling package security.</span></span> <span data-ttu-id="01c3e-116">Os autores de pacote exigeem acesso a apenas uma parte de uma solução de pacote múltiplo.</span><span class="sxs-lookup"><span data-stu-id="01c3e-116">Package authors require access to only a part of a multipackage solution.</span></span> <span data-ttu-id="01c3e-117">Na separação de um pacote em vários, você pode fornecer um nível de segurança maior, porque pode conceder acesso de autor só aos pacotes relevantes.</span><span class="sxs-lookup"><span data-stu-id="01c3e-117">By separating a package into multiple packages, you can provide a greater level of security, because you can grant an author access to only the relevant packages.</span></span>  
  
 <span data-ttu-id="01c3e-118">Um pacote que executa outros pacotes geralmente é chamado de pacote pai, e os pacotes que um fluxo de trabalho pai executa são chamados de pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-118">A package that runs other packages is generally referred to as the parent package, and the packages that a parent workflow runs are called child packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="01c3e-119">inclui tarefas que executam operações de fluxo de trabalho, como a execução de executáveis e arquivos em lote.</span><span class="sxs-lookup"><span data-stu-id="01c3e-119">includes tasks that perform workflow operations, such as executing executables and batch files.</span></span> <span data-ttu-id="01c3e-120">Para obter mais informações, consulte [Execute Process Task](execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-120">For more information, see [Execute Process Task](execute-process-task.md).</span></span>  
  
## <a name="running-packages"></a><span data-ttu-id="01c3e-121">Executando pacotes</span><span class="sxs-lookup"><span data-stu-id="01c3e-121">Running Packages</span></span>  
 <span data-ttu-id="01c3e-122">A tarefa Executar Pacote pode executar pacotes filho contidos no mesmo projeto que contém o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-122">The Execute Package task can run child packages that are contained in the same project that contains the parent package.</span></span> <span data-ttu-id="01c3e-123">Para selecionar um pacote filho do projeto, defina a propriedade **ReferenceType** como **Referência de Projeto**e defina a propriedade **PackageNameFromProjectReference** .</span><span class="sxs-lookup"><span data-stu-id="01c3e-123">You select a child package from the project by setting the **ReferenceType** property to **Project Reference**, and then setting the **PackageNameFromProjectReference** property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01c3e-124">A opção **ReferenceType** é somente leitura e será definida como **Referência Externa** se o projeto que contém o pacote não tiver sido convertido no modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="01c3e-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="01c3e-125">Para obter mais informações sobre conversão, consulte [Implantar projetos no Servidor do Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="01c3e-126">A tarefa Executar Pacote pode executar pacotes armazenados no banco de dados msdb do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e pacotes armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="01c3e-126">The Execute Package task can also run packages stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database and packages stored in the file system.</span></span> <span data-ttu-id="01c3e-127">A tarefa usa um gerenciador de conexões OLE DB para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou um gerenciador de conexões de Arquivo para acessar o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="01c3e-127">The task uses an OLE DB connection manager to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or a File connection manager to access the file system.</span></span> <span data-ttu-id="01c3e-128">Para obter mais informações, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md) e [Flat File Connection Manager](../connection-manager/flat-file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-128">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md) and [Flat File Connection Manager](../connection-manager/flat-file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="01c3e-129">A tarefa Executar Pacote também pode executar um plano de manutenção do banco de dados que permite a administração de pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] e planos de manutenção de banco de dados na mesma solução [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01c3e-129">The Execute Package task can also run a database maintenance plan, which lets you manage both [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages and database maintenance plans in the same [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution.</span></span> <span data-ttu-id="01c3e-130">Um plano de manutenção de banco de dados é semelhante a um pacote do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , mas um plano pode incluir apenas tarefas de manutenção do banco de dados e sempre é armazenado no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="01c3e-130">A database maintenance plan is similar to an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package, but a plan can include only database maintenance tasks, and it is always stored in the msdb database.</span></span>  
  
 <span data-ttu-id="01c3e-131">Se você escolher um pacote armazenado no sistema de arquivos, forneça o nome e o local do pacote.</span><span class="sxs-lookup"><span data-stu-id="01c3e-131">If you choose a package stored in the file system, you must provide the name and location of the package.</span></span> <span data-ttu-id="01c3e-132">O pacote pode residir em qualquer lugar no sistema de arquivos; não tem que estar na mesma pasta que o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-132">The package can reside anywhere in the file system; it does not have to be in the same folder as the parent package.</span></span>  
  
 <span data-ttu-id="01c3e-133">O pacote filho pode ser executado no processo do pacote pai ou em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="01c3e-133">The child package can be run in the process of the parent package, or it can be run in its own process.</span></span> <span data-ttu-id="01c3e-134">A execução do pacote filho em seu próprio processo exige mais memória, mas oferece mais flexibilidade.</span><span class="sxs-lookup"><span data-stu-id="01c3e-134">Running the child package in its own process requires more memory, but it provides more flexibility.</span></span> <span data-ttu-id="01c3e-135">Por exemplo, se o processo filho falhar, o processo pai poderá continuar sendo executado.</span><span class="sxs-lookup"><span data-stu-id="01c3e-135">For example, if the child process fails, the parent process can continue to run.</span></span>  
  
 <span data-ttu-id="01c3e-136">De modo contrário, às vezes você pode desejar que os pacotes pai e filho falhem em conjunto como uma unidade, ou que não incorra a sobrecarga adicional de outro processo.</span><span class="sxs-lookup"><span data-stu-id="01c3e-136">Alternatively, sometimes you want the parent and child packages to fail together as one unit, or you might not want to incur the additional overhead of another process.</span></span> <span data-ttu-id="01c3e-137">Por exemplo, se um processo filho falhar e o processamento subsequente no processo pai do pacote depender do sucesso do processo filho, o pacote filho deveria ser executado no processo do pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-137">For example, if a child process fails and subsequent processing in the parent process of the package depends on success of the child process, the child package should run in the process of the parent package.</span></span>  
  
 <span data-ttu-id="01c3e-138">Por padrão, a Propriedade ExecuteOutOfProcess da tarefa executar pacote é definida como `False` e o pacote filho é executado no mesmo processo que o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-138">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="01c3e-139">Se você definir esta propriedade como `True`, o pacote filho será executado em um processo separado.</span><span class="sxs-lookup"><span data-stu-id="01c3e-139">If you set this property to `True`, the child package runs in a separate process.</span></span> <span data-ttu-id="01c3e-140">Isto pode reduzir a velocidade do lançamento do pacote filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-140">This may slow down the launching of the child package.</span></span> <span data-ttu-id="01c3e-141">Além disso, se você definir a propriedade como `True`, você não poderá depurar o pacote em uma instalação somente ferramentas.</span><span class="sxs-lookup"><span data-stu-id="01c3e-141">In addition, if you set the property to `True`, you cannot debug the package in a tools-only install.</span></span> <span data-ttu-id="01c3e-142">Você deve instalar o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01c3e-142">You must install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="01c3e-143">Para obter mais informações, consulte [Instalar o Integration Services](../install-windows/install-integration-services.md)</span><span class="sxs-lookup"><span data-stu-id="01c3e-143">For more information, see [Install Integration Services](../install-windows/install-integration-services.md)</span></span>  
  
## <a name="extending-transactions"></a><span data-ttu-id="01c3e-144">Estendendo transações</span><span class="sxs-lookup"><span data-stu-id="01c3e-144">Extending Transactions</span></span>  
 <span data-ttu-id="01c3e-145">A transação que o pacote pai usa pode se estender ao pacote filho; logo, o trabalho que ambos os pacotes executa pode ser confirmado ou revertido.</span><span class="sxs-lookup"><span data-stu-id="01c3e-145">The transaction that the parent package uses can extend to the child package; therefore, the work both packages perform can be committed or rolled back.</span></span> <span data-ttu-id="01c3e-146">Por exemplo, o banco de dados insere que as execuções do pacote pai podem ser confirmadas ou revertidas, dependendo das inserções do banco de dados executadas pelo pacote filho, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="01c3e-146">For example, the database inserts that the parent package performs can be committed or rolled back, depending on the database inserts that the child package performs, and vice versa.</span></span> <span data-ttu-id="01c3e-147">Para obter mais informações, consulte [Inherited Transactions](../inherited-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-147">For more information, see [Inherited Transactions](../inherited-transactions.md).</span></span>  
  
## <a name="propagating-logging-details"></a><span data-ttu-id="01c3e-148">Propagando detalhes de log</span><span class="sxs-lookup"><span data-stu-id="01c3e-148">Propagating Logging Details</span></span>  
 <span data-ttu-id="01c3e-149">O pacote filho executado pela tarefa Executar Pacote pode ou não ser configurado para usar log, mas o pacote filho sempre encaminhará os detalhes de log ao pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-149">The child package that the Execute Package task runs may or may not be configured to use logging, but the child package will always forward the log details to the parent package.</span></span> <span data-ttu-id="01c3e-150">Se a tarefa Executar Pacote for configurada para usar log, a tarefa registrará os detalhes de log a partir do pacote filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-150">If the Execute Package task is configured to use logging, the task logs the log details from the child package.</span></span> <span data-ttu-id="01c3e-151">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-151">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md).</span></span>  
  
## <a name="passing-values-to-child-packages"></a><span data-ttu-id="01c3e-152">Passando valores a pacotes filho</span><span class="sxs-lookup"><span data-stu-id="01c3e-152">Passing Values to Child Packages</span></span>  
 <span data-ttu-id="01c3e-153">Com frequência um pacote filho usa valores passados para ele por outro pacote que o chama, normalmente, seu pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-153">Frequently a child package uses values passed to it by another package that calls it, ordinarily its parent package.</span></span> <span data-ttu-id="01c3e-154">Usar valores de um pacote pai é útil nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="01c3e-154">Using values from a parent package is useful in scenarios such as the following:</span></span>  
  
-   <span data-ttu-id="01c3e-155">Partes de um fluxo de trabalho maior são atribuídas a pacotes diferentes.</span><span class="sxs-lookup"><span data-stu-id="01c3e-155">Parts of a larger workflow are assigned to different packages.</span></span> <span data-ttu-id="01c3e-156">Por exemplo, um pacote baixa dados em base noturna, resume os dados, atribui valores de dados resumidos a variáveis e depois passa os valores a outro pacote para processamento adicional dos dados.</span><span class="sxs-lookup"><span data-stu-id="01c3e-156">For example, one package downloads data on a nightly basis, summarizes the data, assigns summary data values to variables, and then passes the values to another package for additional processing of the data.</span></span>  
  
-   <span data-ttu-id="01c3e-157">O pacote pai coordena dinamicamente tarefas em um pacote filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-157">The parent package dynamically coordinates tasks in a child package.</span></span> <span data-ttu-id="01c3e-158">Por exemplo, o pacote pai determina o número de dias em um mês corrente e atribui o número a uma variável, e o pacote filho executa uma tarefa esse número de vezes.</span><span class="sxs-lookup"><span data-stu-id="01c3e-158">For example, the parent package determines the number of days in a current month and assigns the number to a variable, and the child package performs a task that number of times.</span></span>  
  
-   <span data-ttu-id="01c3e-159">Um pacote filho exige acesso aos dados derivados dinamicamente do pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-159">A child package requires access to data that is dynamically derived by the parent package.</span></span> <span data-ttu-id="01c3e-160">Por exemplo, o pacote pai extrai dados de uma tabela e carrega o conjunto de linhas em uma variável, e o pacote filho executa outras operações nos dados.</span><span class="sxs-lookup"><span data-stu-id="01c3e-160">For example, the parent package extracts data from a table and loads the rowset into a variable, and the child package performs additional operations on the data.</span></span>  
  
 <span data-ttu-id="01c3e-161">Você pode usar os métodos a seguir para transmitir valores a um pacote filho:</span><span class="sxs-lookup"><span data-stu-id="01c3e-161">You can use the following methods to pass values to a child package:</span></span>  
  
-   <span data-ttu-id="01c3e-162">**Configurações do Pacote**</span><span class="sxs-lookup"><span data-stu-id="01c3e-162">**Package Configurations**</span></span>  
  
     [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="01c3e-163">fornece um tipo de configuração, a configuração de Variável do Pacote Pai, para transmitir valores de pacotes pai para pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-163">provides a configuration type, the Parent Package Variable configuration, for passing values from parent to child packages.</span></span> <span data-ttu-id="01c3e-164">A configuração é construída no pacote filho e usa uma variável no pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-164">The configuration is built on the child package and uses a variable in the parent package.</span></span> <span data-ttu-id="01c3e-165">A configuração é mapeada para uma variável no pacote filho ou para a propriedade de um objeto no pacote filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-165">The configuration is mapped to a variable in the child package, or to the property of an object in the child package.</span></span> <span data-ttu-id="01c3e-166">A variável também pode ser usada nos scripts usados pela tarefa Script ou pelo componente Script.</span><span class="sxs-lookup"><span data-stu-id="01c3e-166">The variable can also be used in the scripts used by the Script task or Script component.</span></span>  
  
-   <span data-ttu-id="01c3e-167">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="01c3e-167">**Parameters**</span></span>  
  
     <span data-ttu-id="01c3e-168">Você pode configurar a tarefa Executar Pacote para mapear variáveis de pacote pai ou parâmetros, ou parâmetros de projeto, para parâmetros de pacote filho.</span><span class="sxs-lookup"><span data-stu-id="01c3e-168">You can configure the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="01c3e-169">O projeto deve usar o modelo de implantação de projeto e o pacote filho deve ser contido no mesmo projeto que contém o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-169">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span> <span data-ttu-id="01c3e-170">Para obter mais informações, consulte [Execute Package Task Editor](../execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-170">For more information, see [Execute Package Task Editor](../execute-package-task-editor.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="01c3e-171">Se o parâmetro de pacote filho não for confidencial e mapeado para um parâmetro pai confidencial, o pacote filho não será executado.</span><span class="sxs-lookup"><span data-stu-id="01c3e-171">If the child package parameter is not sensitive and is mapped to a parent parameter that is sensitive, the child package will fail to run.</span></span>  
    >   
    >  <span data-ttu-id="01c3e-172">Há suporte para as seguintes condições de mapeamento:</span><span class="sxs-lookup"><span data-stu-id="01c3e-172">The following mapping conditions are supported:</span></span>  
    >   
    >  -   <span data-ttu-id="01c3e-173">O parâmetro de pacote confidencial filho é mapeado para um parâmetro confidencial pai</span><span class="sxs-lookup"><span data-stu-id="01c3e-173">Sensitive, child package parameter is mapped to a sensitive, parent parameter</span></span>  
    > -   <span data-ttu-id="01c3e-174">O parâmetro de pacote confidencial filho é mapeado para um parâmetro não confidencial pai</span><span class="sxs-lookup"><span data-stu-id="01c3e-174">Sensitive, child package parameter is mapped to a non-sensitive, parent parameter</span></span>  
    > -   <span data-ttu-id="01c3e-175">O parâmetro de pacote não confidencial filho é mapeado para um parâmetro não confidencial pai</span><span class="sxs-lookup"><span data-stu-id="01c3e-175">Non-sensitive, child package parameter is mapped to a non-sensitive, parent parameter</span></span>  
  
 <span data-ttu-id="01c3e-176">A variável do pacote pai pode ser definida no escopo da tarefa Executar Pacote ou em um contêiner de pai como o pacote.</span><span class="sxs-lookup"><span data-stu-id="01c3e-176">The parent package variable can be defined in the scope of the Execute Package task or in a parent container such as the package.</span></span> <span data-ttu-id="01c3e-177">Se diversas variáveis estiverem disponíveis com o mesmo nome, a variável definida no escopo da tarefa Executar Pacote será usada, ou a variável que tenha o escopo mais próximo da tarefa.</span><span class="sxs-lookup"><span data-stu-id="01c3e-177">If multiple variables with the same name are available, the variable defined in the scope of the Execute Package task is used, or the variable that is closest in scope to the task.</span></span>  
  
 <span data-ttu-id="01c3e-178">Para obter mais informações, consulte [Usar os valores de variáveis e parâmetros em um pacote filho](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="01c3e-178">For more information, see [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
### <a name="accessing-parent-package-variables"></a><span data-ttu-id="01c3e-179">Acessando variáveis de pacote pai</span><span class="sxs-lookup"><span data-stu-id="01c3e-179">Accessing Parent Package Variables</span></span>  
 <span data-ttu-id="01c3e-180">Os pacotes filho podem acessar variáveis de pacote pai usando a tarefa de Script.</span><span class="sxs-lookup"><span data-stu-id="01c3e-180">Child packages can access parent package variables by using the Script task.</span></span> <span data-ttu-id="01c3e-181">Ao inserir o nome da variável de pacote pai na página **Script** do **Editor da Tarefa de Script**, não inclua **Usuário:** no nome da variável.</span><span class="sxs-lookup"><span data-stu-id="01c3e-181">When you enter the name of the parent package variable on the **Script** page in the **Script Task Editor**, don't include **User:** in the variable name.</span></span> <span data-ttu-id="01c3e-182">Caso contrário, o pacote filho não localizará a variável quando você executar o pacote pai.</span><span class="sxs-lookup"><span data-stu-id="01c3e-182">Otherwise, the child package doesn't locate the variable when you run the parent package.</span></span> <span data-ttu-id="01c3e-183">Para obter mais informações sobre como usar a tarefa Script para acessar variáveis de pacote pai, consulte esta entrada de blog, [SSIS: acessando variáveis em um pacote pai](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/).</span><span class="sxs-lookup"><span data-stu-id="01c3e-183">For more information about using the Script task to access parent package variables, see this blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/).</span></span>  
  
## <a name="configuring-the-execute-package-task"></a><span data-ttu-id="01c3e-184">Configurando a tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="01c3e-184">Configuring the Execute Package Task</span></span>  
 <span data-ttu-id="01c3e-185">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="01c3e-185">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="01c3e-186">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="01c3e-186">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="01c3e-187">Editor da tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="01c3e-187">Execute Package Task Editor</span></span>](../execute-package-task-editor.md)  
  
-   [<span data-ttu-id="01c3e-188">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="01c3e-188">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="01c3e-189">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="01c3e-189">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="01c3e-190">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="01c3e-190">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="related-content"></a><span data-ttu-id="01c3e-191">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="01c3e-191">Related Content</span></span>  

<span data-ttu-id="01c3e-192">Entrada de blog, [SSIS: acessando variáveis em um pacote pai](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), em andyleonard. blog.</span><span class="sxs-lookup"><span data-stu-id="01c3e-192">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span> 
  
  