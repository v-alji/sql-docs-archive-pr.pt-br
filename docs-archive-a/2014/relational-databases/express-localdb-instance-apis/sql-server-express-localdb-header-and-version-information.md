---
title: SQL Server Express informações de cabeçalho e versão do LocalDB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583070"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="aba45-102">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="aba45-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="aba45-103">Não há nenhum arquivo de cabeçalho separado para a API da instância de LocalDB do SQL Server Express; as assinaturas e os códigos de erro da função LocalDB são definidos no arquivo de cabeçalho do SQL Server Native Client (sqlncli.h).</span><span class="sxs-lookup"><span data-stu-id="aba45-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="aba45-104">Para usar a API de instância LocalDB, você deverá incluir o arquivo de cabeçalho sqlncli.h em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="aba45-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="aba45-105">Controle de versão de LocalDB</span><span class="sxs-lookup"><span data-stu-id="aba45-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="aba45-106">A instalação de LocalDB usa um único conjunto de binários por versão principal do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aba45-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="aba45-107">Estas versões LocalDB são mantidas e corrigidas de maneira independente.</span><span class="sxs-lookup"><span data-stu-id="aba45-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="aba45-108">Isto significa que o usuário tem que especificar qual versão de linha de base do LocalDB (quer dizer, a versão principal do SQL Server) ele ou ela estará usando.</span><span class="sxs-lookup"><span data-stu-id="aba45-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="aba45-109">A versão é especificada no formato de versão padrão definido pela classe .NET Framework **System. Version** :</span><span class="sxs-lookup"><span data-stu-id="aba45-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="aba45-110">*principal. secundária [. Build [. revision]]*</span><span class="sxs-lookup"><span data-stu-id="aba45-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="aba45-111">Os dois primeiros números na cadeia de caracteres de versão (*principal* e *secundária*) são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="aba45-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="aba45-112">Os dois últimos números na cadeia de caracteres de versão (*compilação* e *revisão*) são opcionais e padrão para zero se o usuário deixá-los fora. Isso significa que, se o usuário especificar apenas "12,2" como o número de versão de LocalDB, ele será tratado como se o usuário tiver especificado "12.2.0.0".</span><span class="sxs-lookup"><span data-stu-id="aba45-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="aba45-113">A versão para a instalação do LocalDB é definida na chave do Registro MSSQLServer\CurrentVersion na chave do Registro da instância do SQL Server, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="aba45-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="aba45-114">Diversas versões do LocalDB na mesma estação de trabalho têm suporte lado a lado.</span><span class="sxs-lookup"><span data-stu-id="aba45-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="aba45-115">No entanto, o código do usuário sempre usa a DLL de **SQLUserInstance** mais recente disponível no computador local para se conectar às instâncias de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="aba45-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="aba45-116">Localizando a DLL SQLUserInstance</span><span class="sxs-lookup"><span data-stu-id="aba45-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="aba45-117">Para localizar a DLL de **SQLUserInstance** , o provedor do cliente usa a seguinte chave do registro:</span><span class="sxs-lookup"><span data-stu-id="aba45-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="aba45-118">Nesta chave, há uma lista de chaves, uma para cada versão do LocalDB instalada no computador.</span><span class="sxs-lookup"><span data-stu-id="aba45-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="aba45-119">Cada uma dessas chaves é nomeada com o número de versão do LocalDB no formato *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="aba45-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="aba45-120">(por exemplo, a chave para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] é chamada de 12,0).</span><span class="sxs-lookup"><span data-stu-id="aba45-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="aba45-121">Em cada chave de versão há um par de nome-valor `InstanceAPIPath` que define o caminho completo para o arquivo SQLUserInstance.dll instalado com essa versão.</span><span class="sxs-lookup"><span data-stu-id="aba45-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="aba45-122">O exemplo a seguir mostra as entradas do Registro para um computador que tem as versões 11.0 e 12.0 do LocalDB instaladas:</span><span class="sxs-lookup"><span data-stu-id="aba45-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="aba45-123">O provedor do cliente deve encontrar a versão mais recente entre todas as versões instaladas e carregar o arquivo DLL do **SQLUserInstance** a partir do `InstanceAPIPath` valor associado.</span><span class="sxs-lookup"><span data-stu-id="aba45-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="aba45-124">Modo de WOW64 no Windows de 64 bits</span><span class="sxs-lookup"><span data-stu-id="aba45-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="aba45-125">As instalações de 64 bits do LocalDB terão um conjunto adicional de chave do Registro para permitir que aplicativos de 32 bits executados em modo WOW64 (Windows-32-on-Windows-64) usem LocalDB.</span><span class="sxs-lookup"><span data-stu-id="aba45-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="aba45-126">Especificamente, no Windows de 64 bits, o LocalDB MSI criará as chave do Registro a seguir:</span><span class="sxs-lookup"><span data-stu-id="aba45-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="aba45-127">os programas de 64 bits que lêem a `Installed Versions` chave verão os valores que apontam para versões de 64 bits da DLL de **SQLUserInstance** , enquanto os programas de 32 bits (executados em janelas de 64 de bits no modo WOW64) serão redirecionados automaticamente para uma `Installed Versions` chave localizada no `Wow6432Node` Hive.</span><span class="sxs-lookup"><span data-stu-id="aba45-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="aba45-128">Essa chave contém valores que apontam para versões de 32 bits da DLL de **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="aba45-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="aba45-129">Usando LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="aba45-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="aba45-130">A API da instância LocalDB define uma constante chamada LOCALDB_DEFINE_PROXY_FUNCTIONS que automatiza a descoberta e o carregamento da DLL de **SqlUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="aba45-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="aba45-131">A seção de código habilitada por esta constante fornece uma implementação de proxies para cada API do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="aba45-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="aba45-132">As implementações de proxy usam uma função comum para associar a pontos de entrada na DLL de **SqlUserInstance** mais recente instalada e, em seguida, encaminhar as solicitações.</span><span class="sxs-lookup"><span data-stu-id="aba45-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="aba45-133">As funções de proxy só serão habilitadas se a constante LOCALDB_DEFINE_PROXY_FUNCTIONS estiver definida no código de usuário antes de incluir o arquivo sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="aba45-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="aba45-134">A constante deve ser definida em somente um módulo de origem (arquivo .cpp) porque define nomes de função externos para todos os pontos de entrada da API.</span><span class="sxs-lookup"><span data-stu-id="aba45-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="aba45-135">Fornece uma implementação de proxies para cada API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="aba45-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="aba45-136">O exemplo de código a seguir mostra como usar a macro do código de C++ nativo:</span><span class="sxs-lookup"><span data-stu-id="aba45-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
