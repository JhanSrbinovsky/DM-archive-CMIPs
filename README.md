The root structure WAS of this form. From here on, the remains unshown directories/files are more or less per simulation (However some tidying is required)

A significant cause of frustration in managing this data across directories/platforms is the lack of consistency in this structure. I propose that we adopt the same structure across directories/platforms. As a first step, we should refine this structure. Note, I will NOT change anything in the line of CMIP7/ACCESS-ESM1.6/ as that is currently being used by multiple users AND is reasonable anyway


```
├── CMIP6
│   └── archive
│       ├── ACCESS-CM2
│       └── ACCESS-ESM1.5
```
```
├── CMIP7
│   ├── ACCESS-ESM1.6
│   │   ├── development
│   │   ├── production
│   │   └── spinup
```
```
└── non-CMIP
    ├── ACCESS-CM2
    ├── ACCESS-ESM1.5
    ├── CMORised
    └── metadata
```

