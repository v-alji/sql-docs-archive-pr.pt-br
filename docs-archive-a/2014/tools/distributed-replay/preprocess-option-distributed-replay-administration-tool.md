---
title: Opção de pré-processamento (Ferramenta de administração do Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571734"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="087d5-102">Opção de pré-processamento (ferramenta de administração Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="087d5-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="087d5-103">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ferramenta de administração de Distributed Replay, `DReplay.exe` , é uma ferramenta de linha de comando que você pode usar para se comunicar com o Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="087d5-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="087d5-104">Este tópico descreve a opção de linha de comando **preprocess** e a sintaxe correspondente.</span><span class="sxs-lookup"><span data-stu-id="087d5-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="087d5-105">A opção **preprocess** inicia o estágio de pré-processamento.</span><span class="sxs-lookup"><span data-stu-id="087d5-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="087d5-106">Durante esse estágio, o controlador prepara os dados de rastreamento de entrada para retomada contra o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="087d5-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="087d5-107">![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="087d5-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="087d5-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="087d5-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="087d5-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="087d5-109">Parameters</span></span>
 <span data-ttu-id="087d5-110">**-m** *Controller* especifica o nome do computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="087d5-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="087d5-111">Você pode usar "`localhost`" ou "`.`" para fazer referência ao computador local.</span><span class="sxs-lookup"><span data-stu-id="087d5-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="087d5-112">Se o parâmetro **-m** não for especificado, será usado o computador local.</span><span class="sxs-lookup"><span data-stu-id="087d5-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="087d5-113">**-i** *input_trace_file* especifica o caminho completo do arquivo de rastreamento de entrada no controlador, como `D:\Mytrace.trc` .</span><span class="sxs-lookup"><span data-stu-id="087d5-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="087d5-114">O parâmetro **-i** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="087d5-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="087d5-115">Se houver arquivos de substituição no mesmo diretório, eles serão carregados e usados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="087d5-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="087d5-116">Os arquivos devem seguir a convenção de nomenclatura de substituição de arquivo, por exemplo: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="087d5-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="087d5-117">Se você estiver usando a ferramenta de administração em um computador diferente do controlador, precisará copiar os arquivos de rastreamento de entrada no controlador de forma que um caminho local possa ser usado para este parâmetro.</span><span class="sxs-lookup"><span data-stu-id="087d5-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="087d5-118">**-d** *controller_working_dir* especifica o diretório no controlador em que o arquivo intermediário será armazenado.</span><span class="sxs-lookup"><span data-stu-id="087d5-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="087d5-119">O parâmetro **-d** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="087d5-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="087d5-120">Os seguintes requisitos são aplicados:</span><span class="sxs-lookup"><span data-stu-id="087d5-120">The following requirements apply:</span></span>

-   <span data-ttu-id="087d5-121">O diretório deve residir no controlador.</span><span class="sxs-lookup"><span data-stu-id="087d5-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="087d5-122">Você deve especificar o caminho completo, iniciando com uma letra da unidade (por exemplo, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="087d5-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="087d5-123">O caminho não deve terminar com uma barra invertida "`\`".</span><span class="sxs-lookup"><span data-stu-id="087d5-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="087d5-124">Não há suporte para caminhos UNC.</span><span class="sxs-lookup"><span data-stu-id="087d5-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="087d5-125">**-c** *CONFIG_FILE* é o caminho completo do arquivo de configuração de pré-processamento; usado para especificar o local do arquivo de configuração de pré-processamento quando armazenado em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="087d5-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="087d5-126">Esse parâmetro pode ser um caminho UNC ou pode residir localmente no computador onde você executa a ferramenta de administração.</span><span class="sxs-lookup"><span data-stu-id="087d5-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="087d5-127">O parâmetro **-c** não será obrigatório se nenhuma filtragem for necessária, ou se você não desejar modificar o tempo ocioso máximo.</span><span class="sxs-lookup"><span data-stu-id="087d5-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="087d5-128">Sem o parâmetro **-c** , o arquivo de configuração de pré-processamento padrão, `DReplay.exe.preprocess.config`, será usado.</span><span class="sxs-lookup"><span data-stu-id="087d5-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="087d5-129">**-f** *status_interval* especifica a frequência (em segundos) na qual exibir mensagens de status.</span><span class="sxs-lookup"><span data-stu-id="087d5-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="087d5-130">Se **-f** não for especificado, o intervalo padrão será de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="087d5-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="087d5-131">Exemplos</span><span class="sxs-lookup"><span data-stu-id="087d5-131">Examples</span></span>
 <span data-ttu-id="087d5-132">Neste exemplo, o estágio de pré-processamento é iniciado com todas as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="087d5-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="087d5-133">O valor `localhost` indica que o serviço do controlador está em execução no mesmo computador que a ferramenta de administração.</span><span class="sxs-lookup"><span data-stu-id="087d5-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="087d5-134">O parâmetro *input_trace_file* especifica o local dos dados de rastreamento de entrada, `c:\mytrace.trc`.</span><span class="sxs-lookup"><span data-stu-id="087d5-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="087d5-135">Como não há filtragem de arquivo de rastreamento envolvida, o parâmetro **-c** deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="087d5-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="087d5-136">Neste exemplo, o estágio de pré-processamento é iniciado e um arquivo de configuração de pré-processamento modificado é especificado.</span><span class="sxs-lookup"><span data-stu-id="087d5-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="087d5-137">Ao contrário do exemplo anterior, o parâmetro **-c** é usado para apontar para o arquivo de configuração modificado, caso tenha armazenado esse arquivo em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="087d5-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="087d5-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="087d5-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="087d5-139">No arquivo de configuração de pré-processamento modificado, é adicionada uma condição de filtro que filtra sessões de sistema durante reprodução distribuída.</span><span class="sxs-lookup"><span data-stu-id="087d5-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="087d5-140">O filtro é adicionado modificando o elemento `<PreprocessModifiers>` no arquivo de configuração de pré-processamento, `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="087d5-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="087d5-141">O exemplo a seguir mostra um arquivo de configuração modificado:</span><span class="sxs-lookup"><span data-stu-id="087d5-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="087d5-142">Permissões</span><span class="sxs-lookup"><span data-stu-id="087d5-142">Permissions</span></span>
 <span data-ttu-id="087d5-143">Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="087d5-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="087d5-144">Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="087d5-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="087d5-145">Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="087d5-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="087d5-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="087d5-146">See Also</span></span>
 <span data-ttu-id="087d5-147">[Preparar os dados de rastreamento de entrada](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configurar Distributed Replay](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="087d5-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


