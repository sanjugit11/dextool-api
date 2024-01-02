## dextool API
# Get Request
export const apiCallGet = (
    baseUrl: any,
    url: any,
    params = {},
    headers?: any
): Promise<{ [key: string]: any }> =>
    new Promise((resolve, reject) => {
        console.log("formatUrl(url, params)", formatUrl(url, params));
        axios.defaults.baseURL = baseUrl;
        axios
            .get(formatUrl(url, params), headers)
            .then((res) => {
                resolve(res.data);
            })
            .catch((error) => {
                reject(error?.data);
            });
    });
    
# [GET] / v2 / blockchain
const baseurl = "https://open-api.dextools.io/free";
const urlPath = "/v2/blockchain";
const options = {
    headers: {
        'X-BLOBR-KEY': '0vJ6v1k7nFwFiaSe3gXb1MSFqcWxDAYX'
    }
};
const data: any = {       //for dex
    'order': "desc",
    'sort': "name",
}
const dextoolInfo: any = await apiCallGet(baseurl, urlPath, data, options);
console.log("wowwwwwwwww===>", dextoolInfo);
console.log("wowwwwwwwww===>wwwww", dextoolInfo?.data?.results);
        
# [GET] / v2 / blockchain / { chain }
const baseurl = "https://open-api.dextools.io/free";
const urlPath = "/v2/blockchain/bsc";   // ether
const options = {
    headers: {
        'X-BLOBR-KEY': '0vJ6v1k7nFwFiaSe3gXb1MSFqcWxDAYX'
    }
};

const dextoolInfo: any = await apiCallGet(baseurl, urlPath, {}, options);
console.log("wowwwwwwwww===>", dextoolInfo);
console.log("wowwwwwwwww===>wwwww", dextoolInfo?.data?.results);
        
# [GET] / v2 / dex / { chain }
const baseurl = "https://open-api.dextools.io/free";
const urlPath = "/v2/blockchain/bsc";    //ether
const options = {
    headers: {
        'X-BLOBR-KEY': '0vJ6v1k7nFwFiaSe3gXb1MSFqcWxDAYX'
    }
};
const data: any = {       //for dex
    'order': "desc",
    'sort': "name",
}
const dextoolInfo: any = await apiCallGet(baseurl, urlPath, data, options);
console.log("wowwwwwwwww===>", dextoolInfo);
console.log("wowwwwwwwww===>wwwww", dextoolInfo?.data?.results);
        
# [GET] / v2 / pool / { chain }
const baseurl = "https://open-api.dextools.io/free";
const urlPath = "/v2/pool/bsc";  //
const options = {
    headers: {
        'X-BLOBR-KEY': '0vJ6v1k7nFwFiaSe3gXb1MSFqcWxDAYX'
    }
};
const data: any = {       //for dex
    'order': "desc",
    'sort': "creationTime",
    'from': "2023-01-01T00:00:00.000Z",
    "to": "2023-11-01T00:00:00.000Z"
}
const dextoolInfo: any = await apiCallGet(baseurl, urlPath, data, options);
console.log("wowwwwwwwww===>", dextoolInfo);
console.log("wowwwwwwwww===>wwwww", dextoolInfo?.data?.results);


