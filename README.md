Outbreak-Mafia-Code
===================
{
    "name": "Outbreak",
    "author": [
        "Karp Karpity",
        "Crobat"
    ],
    "minplayers": 3,
    "killmsg": "±Virologist: ~Player~ (~Role~) has fallen victim to the outbreak!",
    "killusermsg": "*** You have fallen victim to the outbreak! ***",
    "votemsg": "~Player~ suggests that ~Target~ should be quarantined!",
    "lynchmsg": "±Village: ~Player~ (~Role~) has been quarantined!",
    "drawmsg": "±Virologist: It appears as if everyone has perished. Such is the outcome of a deadly outbreak.",
    "ticks": {
        "night": 35,
        "standby": 35
    },
    "summary": "The village is being terrorized by the mafia, but these  mafia have come  equipped with a secret weapon: a virus. The virus kills  whoever it  infects the next night, but its host is able to infect  someone else  before dying. All the while, shady Drug Dealers, creepy aliens, and  defensive Indians lurk about, each with personal goals of their own.  However, within the village may lie  someone with the capabilities to  help find the virus and the mafia and  quarantine them! No matter what  side you're in, the goal and outcome are  the same: the last side  standing wins, and time is running out! PM Karp  Karpity or Crobat for  any suggestions or bugs.",
    "tips": [
		"Infector: You're the most important member on your team. Make sure your poison and your teammates' kill don't overlap to ensure maximum damage to village.",
		"*** Tips for Aliens ***",
		"Alien Mesmerizer: Your distract is outsped only by Salesman's distract. If you inspect a mafia side, you can PL stall them provided your team has the numbers to control the vote.",
		"UFO: See if you can draw the Prostitute or Salesman to PL you. Since it won't stop your partners' kill, they may see you as clean and PM you. Use this and your non-revealing daykills to your advantage.",
		"*** Tips for Drug Dealers ***",
		"Heroin Addict: You can use your exposes as inspects to help find and kill PRs, or fake-expose someone to get them lynched (this is easier to accomplish than you think). If you are poisoned, get your partners to lynch you. Not only does this give you your high priority unshared kill, but you can still infect, and your partners will have their shared kill as well.",
		"Alcoholic: Protect the Heroin Addict instead of the Meth Dealer.",
		"*** Tips for Village ***",
		"It isn't safe for any PR to claim with Infector, UFO, Alien Mesmerizer, Meth Dealer, or Thunder in. Once those are eliminated, it's best for Police Officer to claim.",
		"Guard: Once the Alien is out, spam your command. Mailman will hax it.",
		"Civilian: If you are poisoned, claim and selfvote (assuming there is no confirmed mafia role). You are already going to die to poison, so you might as well help the village out by getting an expose in."
	],
	"sides": [
        {
            "side": "village",
            "translation": "Village",
            "winmsg": "±Village: ~Players~ have successfully eradicated the disease and reversed the outbreak!"
        },
        {
            "side": "mafia",
            "translation": "Outbreak",
            "winmsg": "±Mafia: The village has fallen as everyone succumbed to the deadly virus of ~Players~..."
        },
        {
            "side": "druggies",
            "translation": "Drug Dealers",
            "winmsg": "±Voices: 'Don't knock it 'til you try it!' ~Players~ have an addiction that no one can break!"
        },
        {
            "side": "alien",
            "translation": "Aliens",
            "winmsg": "±Alien: ~Players~ have taken control of Earth, and  now use it as sacred ground for attacking other planets!"
        },
        {
            "side": "indian",
            "translation": "Indians",
            "winmsg": "±Indian:  ~Players~ have defended their territory and killed all intruders!"
        },
        {
            "side": "nature",
            "translation": "Supernatural",
            "winmsg": "±Earth: The almighty power of the floods and thunderstorms created by ~Players~ have eliminated all life on Earth!"
        }
    ],
    "roles": [
        {
            "role": "villager",
            "translation": "Civilian",
            "side": "village",
            "help": "You  are a villager being terrorized by the mafia and their  deadly virus!  Your goal is to vote in order to quarantine people (remove  them from  the game) and remove all of the mafia and anyone infected!  Since you're  so determined to defend your village, if you get  quarantined, you'll  be able to reveal the role of one other person  before you are removed  from the game!",
            "info": "If lynched, can expose one player during the night before dying. Sided with the Village.",
            "actions": {
                "lynch": {
                    "convertTo": "villager2",
                    "convertmsg": "~Self~ (~Old~) can reveal someone's role to everyone before they are quarantined!"
                }
            }
        },
        {
            "role": "villagercured",
            "translation": "Civilian",
            "side": "village",
			"hide": true,
            "help": "You've been cured and live to see another day! You  are a villager being terrorized by the mafia and their  deadly virus!  Your goal is to vote in order to quarantine people (remove  them from  the game) and remove all of the mafia and anyone infected!  Since you're  so determined to defend your village, if you get  quarantined, you'll  be able to reveal the role of one other person  before you are removed  from the game!",
            "info": "If lynched, can expose one player during the night before dying. Sided with the Village.",
            "actions": {
                "lynch": {
                    "convertTo": "villager2",
                    "convertmsg": "~Self~ (~Old~) can reveal someone's role to everyone before they are quarantined!"
                }
            }
        },
        {
            "role": "villagerp",
            "translation": "Civilian",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You are a villager being terrorized by the  mafia and their  deadly virus! Your goal is to vote in order to  quarantine people  (remove them from the game) and remove all of the  mafia and anyone  infected! Since you're so determined to defend your  village, if you get  quarantined, you'll be able to reveal the role of  one other person  before you are removed from the game!",
            "info": "If lynched, can expose one player during the night before dying. Sided with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "lynch": {
                    "convertTo": "villager2p",
                    "convertmsg": "~Self~ (~Old~) can reveal someone's role to everyone before they are quarantined!"
                }
            }
        },
		{
            "role": "villager3",
            "translation": "Civilian",
            "side": "village",
            "help": "You  are a villager being terrorized by the mafia and their  deadly virus!  Your goal is to vote in order to quarantine people (remove  them from  the game) and remove all of the mafia and anyone infected!  Since you're  so determined to defend your village, if you get  quarantined, you'll  be able to reveal the role of one other person  before you are removed  from the game!",
            "info": "If lynched, can kill one person during the night, outspeeding bodyguards and distractors, before dying. This role has a 25% chance of spawning in place of the other Civilian. Sided with the Village.",
            "actions": {
                "lynch": {
                    "convertTo": "villager4",
                    "convertmsg": "~Self~ (~Old~) is filled with rage and can now kill someone before being quarantined!"
                }
            }
        },
        {
            "role": "villager3cured",
            "translation": "Civilian",
            "side": "village",
			"hide": true,
            "help": "You've been cured and live to see another day! You  are a villager being terrorized by the mafia and their  deadly virus!  Your goal is to vote in order to quarantine people (remove  them from  the game) and remove all of the mafia and anyone infected!  Since you're  so determined to defend your village, if you get  quarantined, you'll  be able to reveal the role of one other person  before you are removed  from the game!",
            "info": "If lynched, can expose one player during the night before dying. Sided with the Village.",
            "actions": {
                "lynch": {
                    "convertTo": "villager4",
                    "convertmsg": "~Self~ (~Old~) is filled with rage and can now kill someone before being quarantined!"
                }
            }
        },
        {
            "role": "villager3p",
            "translation": "Civilian",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You are a villager being terrorized by the  mafia and their  deadly virus! Your goal is to vote in order to  quarantine people  (remove them from the game) and remove all of the  mafia and anyone  infected! Since you're so determined to defend your  village, if you get  quarantined, you'll be able to reveal the role of  one other person  before you are removed from the game!",
            "info": "If lynched, can expose one player during the night before dying. Sided with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "lynch": {
                    "convertTo": "villager4p",
                    "convertmsg": "~Self~ (~Old~) is filled with rage and can now kill someone before being quarantined!"
                }
            }
        },
        {
            "role": "villager2",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "They thought you had the virus and needed to be quarantined. They were wrong, so the panic continues. However, before you're gone for good, you can reveal someone's role by using /expose [name]!",
            "actions": {
                "night": {
                    "expose": {
                        "command": "dummy",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "dummybroadcastmsg": "Before being quarantined, the villager was able  to alert everyone that ~Target~ is the ~TargetRole~!",
                        "pierce": true
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
        {
            "role": "villager2cured",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "You have been cured and live to see another day! They  thought you had the virus and needed to be quarantined.  They were  wrong, so the panic continues. However, before you're gone for  good,  you can reveal someone's role by using /expose [name]!",
            "actions": {
                "night": {
                    "expose": {
                        "command": "dummy",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "dummybroadcastmsg": "Before being quarantined, the villager was able  to alert everyone that ~Target~ is the ~TargetRole~!",
                        "pierce": true
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
        {
            "role": "villager2p",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "They  thought you had the virus and needed to be quarantined.  They were  right! However, before you're gone for good, you can reveal  someone's  role by using /expose [name]! Remember that you can also  spread the  virus in hopes of harming those not on your team using  /infect.",
            "actions": {
                "night": {
                    "expose": {
                        "command": "dummy",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "dummybroadcastmsg": "Before being quarantined, the villager was able  to alert everyone that ~Target~ is the ~TargetRole~!",
                        "pierce": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
		{
            "role": "villager4",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "They thought you had the virus and needed to be quarantined. They were wrong, so the panic continues. However, before you're gone for good, you can kill someone using /kill! This will outspeed bodyguards and distractors, will be broadcasted to everyone, and you won't be able to change your target!",
            "actions": {
                "night": {
                    "kill": {
                        "restrict": ["kill"],
						"broadcast": "*",
						"broadcastmsg": "*** The Civilian has chosen to kill ~Target~! This kill can't be stopped in any way!",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "pierce": true
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
        {
            "role": "villager4cured",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "You have been cured and live to see another day! They  thought you had the virus and needed to be quarantined.  They were  wrong, so the panic continues. However, before you're gone for good, you can kill someone using /kill! This will outspeed bodyguards and distractors, will be broadcasted to everyone, and you won't be able to change your target!",
            "actions": {
                "night": {
                    "kill": {
                        "restrict": ["kill"],
						"broadcast": "*",
						"broadcastmsg": "*** The Civilian has chosen to kill ~Target~! This kill can't be stopped in any way!",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "pierce": true
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
        {
            "role": "villager4p",
            "translation": "Civilian",
            "side": "village",
            "hide": true,
            "help": "They  thought you had the virus and needed to be quarantined.  They were  right! However, before you're gone for good, you can kill someone using /kill! This will outspeed bodyguards and distractors, will be broadcasted to everyone, and you won't be able to change your target! Remember that you can also  spread the  virus in hopes of harming those not on your team using  /infect.",
            "actions": {
                "night": {
                    "kill": {
                        "restrict": ["kill"],
						"broadcast": "*",
						"broadcastmsg": "*** The Civilian has chosen to kill ~Target~! This kill can't be stopped in any way!",
                        "common": "Self",
                        "target": "AnyButSelf",
                        "priority": 1,
                        "pierce": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "You're now quarantined and out of the game!"
                    }
                }
            }
        },
        {
            "role": "stalker",
            "translation": "Detective",
            "side": "village",
            "help": "As  the sleuth of this village, you have been gifted with the ability to  follow  someone without being noticed! For this reason, you can /stalk  one  person during the night to find out who they visited!",
            "info": "Can stalk one person during the night. Sided with the Village.",
            "actions": {
                "night": {
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 24
                    }
                }
            }
        },
        {
            "role": "stalkercured",
            "translation": "Detective",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  the sleuth of this village, you have been gifted with the ability to  follow  someone without being noticed! For this reason, you can /stalk  one  person during the night to find out who they visited!",
            "info": "Can stalk one person during the night. Sided with the Village.",
            "actions": {
                "night": {
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 24
                    }
                }
            }
        },
        {
            "role": "stalkerp",
            "translation": "Detective",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As the sleuth of this village, you have been gifted with the  ability to follow someone without being noticed! For this reason, you   can /stalk one person during the night to find out who they visited!",
            "info": "Can stalk one person during the night. Sided with the Village.",
            "actions": {
                "night": {
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 24
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "inspector",
            "translation": "Police Officer",
            "side": "village",
            "help": "As  a member of the police force, it is your duty to protect this village  and those among it. For this reason, you are able to /inspect one person during the night to determine their role! However, since it is so  dangerous nowadays, you will be successful only 50% of the time.",
            "info": "Can inspect one person during the night (50% fail chance). Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "failChance": 0.5,
                        "priority": 20
                    }
                }
            }
        },
        {
            "role": "inspectorcured",
            "translation": "Police Officer",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  a member of the police force, it is your duty to protect this village  and those within it. For this reason, you are able to /inspect one person  during the night to determine their role! However, since it is so  dangerous nowadays, you will be successful only 50% of the time.",
            "info": "Can inspect one person during the night with a 50% fail chance. Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "failChance": 0.5,
                        "priority": 20,
						"hide": true
                    }
                }
            }
        },
        {
            "role": "inspectorp",
            "translation": "Police Officer",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As a member of the police force, it is your duty to protect  this village and those within it. For this reason, you are able to  /inspect one person during the night to determine their role! However,  since it is so dangerous nowadays, you will be successful only 50% of  the time.",
            "info": "Can inspect one person during the night (50% fail chance). Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "failChance": 0.5,
                        "priority": 20,
						"hide": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "inspector2",
            "translation": "Police Officer",
            "side": "village",
            "help": "As  a member of the police force, it is your duty to protect this village  and those among it. For this reason, you are able to /inspect one person  during the night to determine their role! However, since it is so  dangerous nowadays, you will be able to do this only every other night.",
            "info": "Can inspect one person during the night every other night. This version has a 50% chance of spawning in place of the other Police Officer. Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "recharge": 2,
                        "priority": 18,
						"hide": true
                    }
                }
            }
        },
        {
            "role": "inspector2cured",
            "translation": "Police Officer",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  a member of the police force, it is your duty to protect this village  and those among it. For this reason, you are able to /inspect one person  during the night to determine their role! However, since it is so  dangerous nowadays, you will be able to do this every other night.",
            "info": "Can inspect one person during the night every other night. Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "recharge": 2,
                        "priority": 18,
						"hide": true
                    }
                }
            }
        },
        {
            "role": "inspector2p",
            "translation": "Police Officer",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As a member of the police force, it is your duty to protect  this village and those within it. For this reason, you are able to  /inspect one person during the night to determine their role! However,  since it is so dangerous nowadays, you will be able to do this only four  times.",
            "info": "Can inspect one person during the night 4 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 18,
						"hide": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "bodyguard",
            "translation": "Guard",
            "side": "village",
            "help": "Your  sole purpose is to defend anyone you see fit, so you are able to  /protect up to two people during the night, and three an entire game.",
            "info": "Can protect up to two people during the night, and three an entire game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 3,
                        "limit": 2,
                        "priority": 9
                    }
                }
            }
        },
        {
            "role": "bodyguardcured",
            "translation": "Guard",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! Your  sole purpose is to defend anyone you see fit, so you are able to  /protect up to two people during the night, and three an entire game.",
            "info": "Can protect two people during the night 3 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "limit": 2,
                        "priority": 9
                    }
                }
            }
        },
        {
            "role": "bodyguardp",
            "translation": "Guard",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! Your sole purpose is to defend anyone you see fit, so you  are able to  /protect up to two people during the night, and three an entire game.",
            "info": "Can protect two people during the night 3 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "limit": 2,
                        "priority": 9
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "bodyguard2",
            "translation": "Guard",
            "side": "village",
            "help": "Your  sole purpose is to defend anyone you see fit, so you are able to  /protect two people during the night. You can only do this 4 times  though.",
            "info": "Can protect two people during the night 4 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 4,
                        "limit": 2,
                        "priority": 9
                    }
                }
            }
        },
        {
            "role": "bodyguard2cured",
            "translation": "Guard",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! Your  sole purpose is to defend anyone you see fit, so you are able to  /protect two people during the night. You can only do this 4 times  though.",
            "info": "Can protect two people during the night 4 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 4,
                        "limit": 2,
                        "priority": 9
                    }
                }
            }
        },
        {
            "role": "bodyguard2p",
            "translation": "Guard",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! Your sole purpose is to defend anyone you see fit, so you  are able to /protect two people during the night. You can only do this 4  times though.",
            "info": "Can protect two people during the night 4 times a game. Sided with the Village.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "limit": 2,
                        "priority": 9
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "spy",
            "translation": "Mailman",
            "side": "village",
            "help": "As  the neighborhood mailman, you lead the simple life of delivering mail  to everyone. However, even the simplest of tasks such as this allows you to get hax on kills and protects!",
            "info": "Gets small hax on kill and protect. Sided with the Village.",
            "actions": {
                "hax": {
                    "kill": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    },
                    "protect": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    }
                }
            }
        },
        {
            "role": "spycured",
            "translation": "Mailman",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  the neighborhood mailman, you lead the simple life of delivering mail  to everyone. However, even the simplest of tasks such as this allows you to get hax on kills and protects!",
            "info": "Gets small hax on kill and protect. Sided with the Village.",
            "actions": {
                "hax": {
                    "kill": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    },
                    "protect": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    }
                }
            }
        },
        {
            "role": "spyp",
            "translation": "Mailman",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As the neighborhood mailman, you lead the simple life of  delivering mail to everyone. However, even the simplest of tasks such as this allows you to get hax on kills and protects!",
            "info": "Gets small hax on kill and protect. Sided with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "hax": {
                    "kill": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    },
                    "protect": {
                        "revealTeam": 0.2,
                        "revealPlayer": 0.1
                    }
                }
            }
        },
        {
            "role": "mayor",
            "translation": "President",
            "side": "village",
            "help": "You  are the leader of this village being terrorized by the  mafia and their  deadly virus! Your authority and prestige give you a  vote of 3, and since you're married to the First Lady, you know her identity and can talk to her using /tt.",
            "info": "Vote of 3. Knows First Lady. Sided with the Village.",
            "actions": {
                "vote": 3,
                "teamTalk": ["neighbor", "neighborcured", "neighborp"],
                "startup": {
                    "revealRole": [
                        "neighbor",
						"neighborcured",
						"neighborp"
                    ]
                }
            }
        },
        {
            "role": "mayorcured",
            "translation": "President",
            "side": "village",
			"hide": true,
            "help": "You  are the leader of this village being terrorized by the  mafia and their  deadly virus! Your authority and prestige give you a  vote of 3, and since you're married to the First Lady, you know her identity and can talk to her using /tt.",
            "info": "Vote of 3. Knows First Lady. Sided with the Village.",
            "actions": {
                "vote": 3,
                "teamTalk": ["neighbor", "neighborcured", "neighborp"],
                "startup": {
                    "revealRole": [
                        "neighbor",
						"neighborcured",
						"neighborp"
                    ]
                }
            }
        },
        {
            "role": "mayorp",
            "translation": "President",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You  are the leader of this village being terrorized by the  mafia and their  deadly virus! Your authority and prestige give you a  vote of 3, and since you're married to the First Lady, you know her identity and can talk to her using /tt.",
            "info": "Vote of 3. Knows First Lady. Sided with the Village.",
            "actions": {
                "vote": 3,
                "teamTalk": ["neighbor", "neighborcured", "neighborp"],
                "startup": {
                    "revealRole": [
                        "neighbor",
						"neighborcured",
						"neighborp"
                    ]
                },            
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
						"broadcast": ["neighbor", "neighborcured", "neighborp"],
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "exposer",
            "translation": "Firefighter",
            "side": "village",
            "help": "As  a fanner of flames, you have been tasked with rescuing others from  fires. Just to be sure you get your job done properly, you are able to  use /rescue on someone during the day to reveal their role as you save  them! You can only do this twice.",
            "info": "Can  rescue (expose) one person during the standby (user is not revealed) twice per game. Sided with the  Village.",
            "actions": {
                "standby": {
                    "rescue": {
                        "command": "expose",
                        "target": "AnyButSelf",
                        "msg": "IT'S HERO TIME! Use /rescue to save someone from a fire and reveal their role as well!",
                        "charges": 2,
                        "exposemsg": "'Don't worry, ~Target~, I will save you! You are the ~Role~ that needed rescuing right?'"
                    }
                }
            }
        },
        {
            "role": "exposercured",
            "translation": "Firefighter",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  a fanner of flames, you have been tasked with rescuing others from  fires. Just to be sure you get your job done properly, you are able to  use /rescue on someone during the day to reveal their role as you save  them! You can only do this twice.",
            "info": "Can  rescue (expose) one person during the standby to reveal  their role  (user is not revealed) twice per game. Sided with the  Village.",
            "actions": {
                "standby": {
                    "rescue": {
                        "command": "expose",
                        "target": "AnyButSelf",
                        "msg": "IT'S HERO TIME! Use /rescue to save someone from a fire and reveal their role as well!",
                        "exposemsg": "'Don't worry, ~Target~, I will save you! You are the ~Role~ that needed rescuing right?'"
                    }
                }
            }
        },
        {
            "role": "exposerp",
            "translation": "Firefighter",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As a fanner of flames, you have been tasked with rescuing  others from fires. Just to be sure you get your job done properly, you  are able to use /rescue on someone during the day to reveal their role  as you save them! You can only do this twice.",
            "info": "Can  rescue (expose) one person during the standby to reveal  their role  (user is not revealed) twice per game. Sided with the  Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "standby": {
                    "rescue": {
                        "command": "expose",
                        "target": "AnyButSelf",
                        "msg": "IT'S HERO TIME! Use /rescue to save someone from a fire and reveal their role as well!",
                        "exposemsg": "'Don't worry, ~Target~, I will save you! You are the ~Role~ that needed rescuing right?'"
                    }
                }
            }
        },
        {
            "role": "neighbor",
            "translation": "First Lady",
            "side": "village",
            "help": "As  the symbol of the village, you are able to /whisper to someone during  the night to reveal your  role to them! Since you're married to the President, you know his identity and can talk to him using /tt. Best of luck in finding and  connecting with your  teammates!",
            "info": "Can whisper to one person during the night to send a message  to them confirming their role. Knows President. Sided with the Village.",
            "actions": {
                "teamTalk": ["mayor", "mayorcured", "mayorp"],
                "startup": {
                    "revealRole": [
                        "mayor",
						"mayorcured",
						"mayorp"
                    ]
                },
				"night": {
                    "whisper": {
                        "command": "dummy",
                        "common": "Self",
						"broadcast": ["mayor", "mayorcured", "mayorp"],
                        "target": "AnyButSelf",
                        "priority": 21,
                        "dummytargetmsg": "Psssssst. ~Target~, are you there? It's ~Self~, the  First Lady. Help me to get rid of the mafia and their virus!"
                    }
                }
            }
        },
        {
            "role": "neighborcured",
            "translation": "First Lady",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! As  the symbol of the village, you are able to /whisper to someone during  the night to reveal your  role to them! Since you're married to the President, you know his identity and can talk to him using /tt. Best of luck in finding and  connecting with your  teammates!",
            "info": "Can whisper to one person during the night to send a message  to them confirming their role. Knows President. Sided with the Village.",
            "actions": {
                "teamTalk": ["mayor", "mayorcured", "mayorp"],
                "startup": {
                    "revealRole": [
                        "mayor",
						"mayorcured",
						"mayorp"
                    ]
                },
				"night": {
                    "whisper": {
                        "command": "dummy",
                        "common": "Self",
						"broadcast": ["mayor", "mayorcured", "mayorp"],
                        "target": "AnyButSelf",
                        "priority": 21,
                        "dummytargetmsg": "Psssssst. ~Target~, are you there? It's ~Self~, the  First Lady. Help me to get rid of the mafia and their virus!"
                    }
                }
            }
        },
        {
            "role": "neighborp",
            "translation": "First Lady",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! As the symbol of the village, you are able to /whisper to  someone during the  night to reveal your role to them! Since you're married to the President, you know his identity and can talk to him using /tt. Best of luck in finding and  connecting with your  teammates!",
            "info": "Can whisper to one person during the night to send a message  to them confirming their role. Knows President. Sided with the Village.",
            "actions": {
                "teamTalk": ["mayor", "mayorcured", "mayorp"],
                "startup": {
                    "revealRole": [
                        "mayor",
						"mayorcured",
						"mayorp"
                    ]
                },
				"night": {
                    "whisper": {
                        "command": "dummy",
                        "common": "Self",
						"broadcast": ["mayor", "mayorcured", "mayorp"],
                        "target": "AnyButSelf",
                        "priority": 21,
                        "dummytargetmsg": "Psssssst. ~Target~, are you there? It's ~Self~, the  First Lady. Help me to get rid of the mafia and their virus!"
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
						"broadcast": ["mayor", "mayorcured", "mayorp"],
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "samurai",
            "translation": "Soldier",
            "side": "village",
            "help": "A  seasoned veteran of warfare, you fight for your country! Your  patriotism and background grant you the ability to /kill during the day!  However, your acts will be in plain sight which will reveal you and you  can only kill three times a game.",
            "info": "Can kill one person during the standby (user is revealed) three times per game. Sided with the Village.",
            "actions": {
                "standby": {
                    "kill": {
                        "target": "AnyButSelf",
                        "msg": "Your  patriotism shines bright! Time to unleash it and kill someone in the  name of the village using /kill! Remember that you can only use this three times a game and it will reveal you!",
                        "limit": 1,
                        "charges": 3,
                        "killmsg": "'LONG LIVE THE VILLAGE!!!!' ~Self~ charges toward ~Target~ and kills them in fierce close combat!"
                    }
                }
            }
        },
        {
            "role": "samuraicured",
            "translation": "Soldier",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! A  seasoned veteran of warfare, you fight for your country! Your  patriotism and background grant you the ability to /kill during the day!  However, your acts will be in plain sight which will reveal you and you  can only kill three times a game.",
            "info": "Can kill one person during the standby twice per game. Sided with the Village.",
            "actions": {
                "standby": {
                    "kill": {
                        "target": "AnyButSelf",
                        "msg": "Your  patriotism shines bright! Time to unleash it and kill someone in the  name of the village using /kill! Remember that you can only use this three times a game and it will reveal you!",
                        "limit": 1,
                        "killmsg": "'LONG LIVE THE VILLAGE!!!!' ~Self~ charges toward ~Target~ and kills them in fierce close combat!"
                    }
                }
            }
        },
        {
            "role": "samuraip",
            "translation": "Soldier",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! A seasoned veteran of warfare, you fight for your country!  Your patriotism and background grant you the ability to /kill during the  day! You can also /stab someone during the day to kill them as well!  However, your acts will be in plain sight which will reveal you and you  can only kill three times a game.",
            "info": "Can kill one person during the standby twice per game. Sided with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "standby": {
                    "kill": {
                        "target": "AnyButSelf",
                        "msg": "Your  patriotism shines bright! Time to unleash it and kill someone in the  name of the village using /kill! Remember that you can only use this three times a game and it will reveal you!",
                        "limit": 1,
                        "killmsg": "'LONG LIVE THE VILLAGE!!!!' ~Self~ charges toward ~Target~ and kills them in fierce close combat!"
                    }
                }
            }
        },
        {
            "role": "vigilante",
            "translation": "Assassin",
            "side": "village",
            "help": "You  are a villager being terrorized by the mafia and their  deadly virus!  However, you're fed up with hiding and you're ready to  fight back! For  these reasons, you are able to /kill up to 3 people  during a night and  during the entire game!",
            "info": "Can kill up to three people during the night and during a game. Sided with the Village.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 3,
                        "limit": 3,
                        "priority": 16
                    }
                }
            }
        },
        {
            "role": "vigilantecured",
            "translation": "Assassin",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! You  are a villager being terrorized by the mafia and their  deadly virus!  However, you're fed up with hiding and you're ready to  fight back! For  these reasons, you are able to /kill up to 3 people  during a night and  during the entire game!",
            "info": "Can kill up to three people during the night and during a game. Sided with the Village.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "limit": 3,
                        "priority": 16
                    }
                }
            }
        },
        {
            "role": "vigilantep",
            "translation": "Assassin",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You are a villager being terrorized by the  mafia and their  deadly virus! However, you're fed up with hiding and  you're ready to  fight back! For these reasons, you are able to /kill up  to 3 people  during a night and during the entire game!",
            "info": "Can kill up to three people during the night and during a game. Sided with the Village.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "limit": 3,
                        "priority": 16
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "hooker",
            "translation": "Prostitute",
            "side": "village",
            "help": "Charming,  witty, alluring. Your characteristics and poor life choices have lead  you down this route. However, it isn't all bad. You are able to  /distract one person during the night to stop  them from doing any  actions! Of course, not everyone is interested in you, so this  command has a 20% chance to fail.",
            "info": "Can distract one person during the night (20% fail chance). Sided with the Village.",
            "actions": {
                "night": {
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 5,
                        "failChance": 0.2,
                        "distractmsg": "You weren't able to do anything during the night as you  were charmed by the Prostitute!",
                        "teammsg": "Your partner was completely charmed by the Prostitute and  you spent the entire night trying to get them to snap out of it!"
                    }
                }
            }
        },
        {
            "role": "hookercured",
            "translation": "Prostitute",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! Charming,  witty, alluring. Your characteristics and poor life choices have lead  you down this route. However, it isn't all bad. You are able to  /distract one person during the night to stop  them from doing any  actions! Of course, not everyone is interested in you, so this  command has a 20% chance to fail.",
            "info": "Can distract one person during the night (20% fail chance). Sided with the Village.",
            "actions": {
                "night": {
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 5,
                        "failChance": 0.2,
                        "distractmsg": "You weren't able to do anything during the night as you  were charmed by the Prostitute!",
                        "teammsg": "Your partner was completely charmed by the Prostitute and  you spent the entire night trying to get them to snap out of it!"
                    }
                }
            }
        },
        {
            "role": "hookerp",
            "translation": "Prostitute",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! Charming, witty, alluring. Your characteristics and poor  life choices have lead you down this route. However, it isn't all bad.  You are able to /distract one person during the night to stop  them from  doing any actions! Of course, not everyone is interested in you, so this command has a 20% chance to fail.",
            "info": "Can distract one person during the night (20% fail chance). Sided with the Village.",
            "actions": {
                "night": {
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 5,
                        "failChance": 0.2,
                        "distractmsg": "You weren't able to do anything during the night as you  were charmed by the Prostitute!",
                        "teammsg": "Your partner was completely charmed by the Prostitute and  you spent the entire night trying to get them to snap out of it!"
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                }
            }
        },
        {
            "role": "joat",
            "translation": "Salesman",
            "side": "village",
            "help": "You've  traveled far and wide along this world and this has  allowed you to  learn several abilities. You are able to /safeguard,  /distract,  /protect, /kill, /inspect, /poison, and /stalk, but you can  only do  each of these one time. Collect information with these skills  and use  it to eliminate the mafia!",
            "info": "Can  use all of the following commands once a game during the  night:  safeguard, distract, protect, kill, inspect, poison, and stalk.  Sided  with the Village.",
            "actions": {
                "night": {
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 2
                    },
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 6
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 10
                    },
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 17
                    },
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 20
                    },
                    "poison": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 23
                    },
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "charges": 1,
                        "priority": 26
                    }
                }
            }
        },
        {
            "role": "joatcured",
            "translation": "Salesman",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! You've  traveled far and wide along this world and this has  allowed you to  learn several abilities. You are able to /safeguard,  /distract,  /protect, /kill, /inspect, /poison, and /stalk, but you can  only do  each of these one time. Collect information with these skills  and use  it to eliminate the mafia!",
            "info": "Can  use all of the following commands once a game during the  night:  safeguard, distract, protect, kill, inspect, poison, and stalk.  Sided  with the Village.",
            "actions": {
                "night": {
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 2
                    },
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 6
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 10
                    },
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 17
                    },
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 20
                    },
                    "poison": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 23
                    },
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 26
                    }
                }
            }
        },
        {
            "role": "joatp",
            "translation": "Salesman",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You've traveled far and wide along this world  and this has  allowed you to learn several abilities. You are able to  /safeguard,  /distract, /protect, /kill, /inspect, /poison, and /stalk,  but you can  only do each of these one time. Collect information with  these skills  and use it to eliminate the mafia!",
            "info": "Can  use all of the following commands once a game during the  night:  safeguard, distract, protect, kill, inspect, poison, and stalk.  Sided  with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    },
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 2
                    },
                    "distract": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 3
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 10
                    },
                    "kill": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 17
                    },
                    "inspect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 20
                    },
                    "poison": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 23
                    },
                    "stalk": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 26
                    }
                }
            }
        },
        {
            "role": "miller",
            "translation": "Hoodlum",
            "side": "village",
            "help": "You're  nothing more than a young ruffian, a common thief. While you steal, you  have no intention of killing or harming anyone. Due to your shady  behavior though, others will see you as the mafia.",
            "info": "Reveals as any mafia role when inspected. Sided with the Village.",
            "actions": {
                "inspect": {
                    "revealAs": ["alien", "alienm", "ufo", "alcohol", "heroin", "meth", "chief", "head", "indian", "infector", "mafia2", "savage", "light", "rain", "thunder"]
                }
            }
        },
        {
            "role": "millercured",
            "translation": "Hoodlum",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! You're  nothing more than a young ruffian, a common thief. While you steal, you  have no intention of killing or harming anyone. Due to your shady  behavior though, others will see you as the mafia.",
            "info": "Reveals as Outbreak Mastermind when inspected. Sided with the Village.",
            "actions": {
                "inspect": {
                    "revealAs": ["alien", "alienm", "ufo", "alcohol", "heroin", "meth", "chief", "head", "indian", "infector", "mafia2", "savage", "light", "rain", "thunder"]
                }
            }
        },
        {
            "role": "millerp",
            "translation": "Hoodlum",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You're nothing more than a young ruffian, a common thief.  While you steal, you have no intention of killing or harming anyone. Due  to your shady behavior though, others will see you as the mafia.",
            "info": "Reveals as Outbreak Mastermind when inspected. Sided with the Village.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    }
                },
                "inspect": {
                    "revealAs": ["alien", "alienm", "ufo", "alcohol", "heroin", "meth", "chief", "head", "indian", "infector", "mafia2", "savage", "light", "rain", "thunder"]
                }
            }
        },
        {
            "role": "detoxer",
            "translation": "Medic",
            "side": "village",
            "help": "A  specialist in the medical field, your duty is to cure others of poison  in hopes of reducing the spreading of the virus. You can do this when  you /examine one person during the night (every 2 nights). Since you will cure them, this will also reveal their role to you. Furthermore, you have a 50% chance to evade poison.",
            "info": "Can examine (inspect + detox) one person during the night every 2 nights. Has a 50% chance to evade poison. Sided with the Village.",
            "actions": {
                "night": {
                    "examine": {
                        "command": [
                            "inspect",
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 27,
                        "recharge": 2,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "pierce": true,
                        "msg": "~Target~ was cured of poison!",
                        "targetmsg": "The doctor cured you of poison!",
                        "detoxmsg": "The doctor cured ~Target~ of poison!"
                    }
                },
                "poison": {
                    "mode": {
                        "evadeChance": 0.5
                    }
                }
            }
        },
        {
            "role": "detoxercured",
            "translation": "Medic",
            "side": "village",
			"hide": true,
            "help": "You have been cured and live to see another day! A  specialist in the medical field, your duty is to cure others of poison  in hopes of reducing the spreading of the virus. You can do this when you /examine one person during the night (every 2 nights). Since you will cure them,  this will also reveal their role to you. Furthermore, you have a 50% chance to evade poison.",
            "info": "Can examine (inspect + detox) one person during the night every 2 nights. Sided with the Village.",
            "actions": {
                "night": {
                    "examine": {
                        "command": [
                            "inspect",
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "recharge": 2,
                        "priority": 27,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "pierce": true,
                        "msg": "~Target~ was cured of poison!",
                        "targetmsg": "The doctor cured you of poison!",
                        "detoxmsg": "The doctor cured ~Target~ of poison!"
                    }
                },
                "poison": {
                    "mode": {
                        "evadeChance": 0.5
                    }
                }
            }
        },
        {
            "role": "detoxerp",
            "translation": "Medic",
            "side": "village",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! A specialist in the medical field, your duty is to cure  others of poison in hopes of reducing the spreading of the virus. You  can do this when you /examine one person during the night. Since you  will cure them, this will also reveal their role to you. Furthermore, you have a 50% chance to evade poison.",
            "info": "",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "pierce": true,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"charges": 1,						
						"hide": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
                    "examine": {
                        "command": [
                            "inspect",
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 27,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "msg": "~Target~ was cured of poison!",
                        "targetmsg": "The doctor cured you of poison!",
                        "detoxmsg": "The doctor cured ~Target~ of poison!"
                    }
                }
            }
        },
		{
			"role": "bombnight",
			"translation": "Chemist",
			"side": "village",
			"help": "With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the night, you will take them down with you! If you want to change that, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all nightkills. Can use /nitrite (convert) to revenge all daykills. Can use /phosphate (convert) to kill the first voter if lynched. Can't be distracted. Sided with the Village.",
			"actions": {
				"kill": {
							"mode": "killattacker",
							"msg": "'You dare to kill me? I, the Chemist, shall take you down with me then!' Before you can even react, there is a sudden explosion, and both you and the Chemist are killed in it."
				},
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombnight"
						],
						"pierce": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombnight"
						],
						"pierce": true,
						"silent": true
					}
				}
			}
		},
		{
			"role": "bombnightcured",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You have been cured and live to see another day! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the night, you will take them down with you! If you want to change that, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all nightkills. Can use /nitrite (convert) to revenge all daykills. Can use /phosphate (convert) to kill the first voter if lynched. Sided with the Village.",
			"actions": {
				"kill": {
							"mode": "killattacker",
							"msg": "'You dare to kill me? I, the Chemist, shall take you down with me then!' Before you can even react, there is a sudden explosion, and both you and the Chemist are killed in it."
				},
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombnightcured"
						],
						"hide": true,
						"pierce": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombnightcured"
						],
						"hide": true,
						"pierce": true,
						"silent": true
					}
				}
			}
		},		
		{
			"role": "bombnightp",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the night, you will take them down with you! If you want to change that, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all nightkills. Can use /nitrite (convert) to revenge all daykills. Can use /phosphate (convert) to kill the first voter if lynched. Sided with the Village.",
			"actions": {
				"kill": {
							"mode": "killattacker",
							"msg": "'You dare to kill me? I, the Chemist, shall take you down with me then!' Before you can even react, there is a sudden explosion, and both you and the Chemist are killed in it."
				},
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "pierce": true,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
                        "pierce": true,
						"charges": 1,						
						"hide": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombnightp"
						],
						"hide": true,
						"pierce": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombnightp"
						],
						"hide": true,
						"pierce": true,
						"silent": true
					}
				}
			}
		},
		{
			"role": "bombday",
			"translation": "Chemist",
			"side": "village",
			"help": "With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the day, you will take them down with you! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all daykills. Can use /hydroxide (convert) to revenge all nightkills. Can use /phosphate (convert) to kill the first voter if lynched. Can't be distracted. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombday"
						],
						"pierce": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombday"
						],
						"pierce": true,
						"silent": true
					}
				},				
				"daykill": "bomb",
				"daykillrevengemsg": "~Target~ attacked ~Self~, but the chemicals ~Self~ made exploded. ~Target~ was caught in the massive explosion and taken down as well!"				
			}
		},
		{
			"role": "bombdaycured",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You have been cured and live to see another day! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the day, you will take them down with you! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all daykills. Can use /hydroxide (convert) to revenge all nightkills. Can use /phosphate (convert) to kill the first voter if lynched. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombdaycured"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombdaycured"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					}
				},				
				"daykill": "bomb",
				"daykillrevengemsg": "~Target~ attacked ~Self~, but the chemicals ~Self~ made exploded. ~Target~ was caught in the massive explosion and taken down as well!"				
			}
		},
		{
			"role": "bombdayp",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, if anyone kills you during the day, you will take them down with you! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /phosphate [your name] to transform your compound into one that will kill the first person to vote you if you are lynched. You also can't be distracted!",
			"info": "Revenges all daykills. Can use /hydroxide (convert) to revenge all nightkills. Can use /phosphate (convert) to kill the first voter if lynched. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "pierce": true,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]                        
                        },
                        "silent": true,
                        "pierce": true,
						"charges": 1,						
						"hide": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["phosphate"],
						"canConvert": [
							"bombdayp"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					},
					"phosphate": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombvote",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombdayp"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					}
				},				
				"daykill": "bomb",
				"daykillrevengemsg": "~Target~ attacked ~Self~, but the chemicals ~Self~ made exploded. ~Target~ was caught in the massive explosion and taken down as well!"				
			}
		},
		{
			"role": "bombvote",
			"translation": "Chemist",
			"side": "village",
			"help": "With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, you will kill the first person to vote you if you are lynched! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. You also can't be distracted!",
			"info": "Kills the first voter if lynched. Can use /hydroxide (convert) to revenge all nightkills. Can use /nitrite (convert) to revenge all daykills. Can't be distracted. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombvote"
						],
						"pierce": true,
						"silent": true
					},
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombvote"
						],
						"pierce": true,
						"silent": true
					}
				},
				"lynch": {
                    "killVoters": {
                        "first": 1,
                        "last": 0,
                        "message": "The attempt to quarantine ~Self~ didn't go quite smoothly. ~Self~ was able to quickly concoct a small explosive and attach it to their shirt before charging at ~Target~. Everyone else took cover as both ~Self~ and ~Target~ were killed in the ensuing massive explosion."
					}
				}
			}
		},
		{
			"role": "bombvotecured",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You have been cured and live to see another day! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, you will kill the first person to vote you if you are lynched! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. You also can't be distracted!",
			"info": "Kills the first voter if lynched. Can use /hydroxide (convert) to revenge all nightkills. Can use /nitrite (convert) to revenge all daykills. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombvotecured"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					},
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombvotecured"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					}
				},
				"lynch": {
                    "killVoters": {
                        "first": 1,
                        "last": 0,
                        "message": "The attempt to quarantine ~Self~ didn't go quite smoothly. ~Self~ was able to quickly concoct a small explosive and attach it to their shirt before charging at ~Target~. Everyone else took cover as both ~Self~ and ~Target~ were killed in the ensuing massive explosion."
					}
				}
			}
		},
		{
			"role": "bombvotep",
			"translation": "Chemist",
			"side": "village",
			"hide": true,
			"help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! With your superior skills with chemicals, you are able to concoct any deadly compound you desire, and change it as you please. Right now, you will kill the first person to vote you if you are lynched! If you want to change that, you can use /hydroxide [your name] to transform your compound into one that will revenge any nightkiller. Otherwise, you can use /nitrite [your name] to transform your compound into one that will revenge any daykiller. You also can't be distracted!",
			"info": "Kills the first voter if lynched. Can use /hydroxide (convert) to revenge all nightkills. Can use /nitrite (convert) to revenge all daykills. Sided with the Village.",
			"actions": {
				"distract": {
                    "mode": "ignore"
                },
				"night": {
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 7,
                        "pierce": true,
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"infectorsmallp": [
								"infectorsmall"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
                        "pierce": true,
						"charges": 1,						
						"hide": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
					"hydroxide": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombnight",
						"cancel": ["nitrite"],
						"canConvert": [
							"bombvotep"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					},
					"nitrite": {
						"command": "convert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 8,
						"newRole": "bombday",
						"cancel": ["hydroxide"],
						"canConvert": [
							"bombvotep"
						],
						"pierce": true,
						"hide": true,
						"silent": true
					}
				},
				"lynch": {
                    "killVoters": {
                        "first": 1,
                        "last": 0,
                        "message": "The attempt to quarantine ~Self~ didn't go quite smoothly. ~Self~ was able to quickly concoct a small explosive and attach it to their shirt before charging at ~Target~. Everyone else took cover as both ~Self~ and ~Target~ were killed in the ensuing massive explosion."
					}
				}
			}
		},
        {
            "role": "mafia2",
            "translation": "Outbreak Mastermind",
            "side": "mafia",
            "help": "You're  here to infiltrate and take over this village! Luckily  for you, you  came equipped with an additional secret weapon: a deadly  virus. It  resides within one of your teammates, and they can use it to  infect a  villager before they die! Use /kill during the night to  eliminate  someone (shared with your teammates)! Just in case your teammates get infected, you can cure them with the antidote you brought using /heal! However, you can only use this twice a game. (Use /tt to  talk to your  teammates.)",
            "info": "Can kill one person during the night. Can heal (detox) one person during the night (twice a game). Sided with the Outbreak.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    },
                    "heal": {
                        "command": [
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 20,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "charges": 2,
                        "silent": true
                    }
                }
            }
        },
        {
            "role": "mafia2cured",
            "translation": "Outbreak Mastermind",
            "side": "mafia",
			"hide": true,
            "help": "You have been cured and live to see another day! You're  here to infiltrate and take over this village! Luckily  for you, you  came equipped with an additional secret weapon: a deadly  virus. It  resides within one of your teammates, and they can use it to  infect a  villager before they die! Use /kill during the night to  eliminate  someone (shared with your teammates)! Just in case your teammates get infected, you can cure them with the antidote you brought using /heal! However, you can only use this twice a game. (Use /tt to  talk to your  teammates.)",
            "info": "Can kill one person during the night. Can heal (detox) one person during the night (twice a game). Sided with the Outbreak.",
            "actions": {
                "preventTeamvote": true,
				"startup": "team-reveal-with-roles",
                "teamTalk": true,
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    },
                    "heal": {
                        "command": [
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 20,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "charges": 2,
                        "silent": true
                    }
                }
            }
        },
        {
            "role": "mafia2p",
            "translation": "Outbreak Mastermind",
            "side": "mafia",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're  cured, you will  die the next night! However, you yourself may spread the  virus in hopes  of infecting those not on your team using /infect, but  you can only do  this once! You're here to infiltrate and take over this  village!  Luckily for you, you came equipped with an additional secret  weapon: a  deadly virus. It resides within one of your teammates, and  they can use  it to infect a villager before they die! Use /kill during  the night to  eliminate someone (shared with your teammates)! Just in case your teammates get infected, you can cure them with the antidote you brought using /heal! However, you can only use this twice a game. (Use /tt to talk to  your teammates.)",
            "info": "Can kill one person during the night. Can heal (detox) one person during the night (twice a game). Sided with the Outbreak.",
            "actions": {
                "preventTeamvote": true,
				"startup": "team-reveal-with-roles",
                "teamTalk": true,
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The  dreaded outbreak continues..."
                    },
                    "heal": {
                        "command": [
                            "detox",
                            "convert"
                        ],
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 20,
                        "newRole": {
                            "villagercured": [
                                "villagerp"
                            ],
                            "detoxercured": [
                                "detoxerp"
                            ],
                            "raincured": [
                                "rainp"
                            ],
                            "stalkercured": [
                                "stalkerp"
                            ],
                            "inspectorcured": [
                                "inspectorp"
                            ],
                            "inspector2cured": [
                                "inspector2p"
                            ],
                            "bodyguardcured": [
                                "bodyguardp"
                            ],
                            "bodyguard2cured": [
                                "bodyguard2p"
                            ],
                            "spycured": [
                                "spyp"
                            ],
                            "mayorcured": [
                                "mayorp"
                            ],
                            "exposercured": [
                                "exposerp"
                            ],
                            "neighborcured": [
                                "neighborp"
                            ],
                            "samuraicured": [
                                "samuraip"
                            ],
                            "vigilantecured": [
                                "vigilantep"
                            ],
                            "hookercured": [
                                "hookerp"
                            ],
                            "joatcured": [
                                "joatp"
                            ],
                            "millercured": [
                                "millerp"
                            ],
                            "mafia2cured": [
                                "mafia2p"
                            ],
                            "infectorcured": [
                                "infectorp"
                            ],
                            "savagecured": [
                                "savagep"
                            ],
                            "methcured": [
                                "methp"
                            ],
                            "alcoholcured": [
                                "alcoholp"
                            ],
                            "heroincured": [
                                "heroinp"
                            ],
                            "aliencured": [
                                "alienp"
                            ],
                            "ufocured": [
                                "ufop"
                            ],
                            "alienmcured": [
                                "alienmp"
                            ],
                            "indiancured": [
                                "indianp"
                            ],
                            "chiefcured": [
                                "chiefp"
                            ],
                            "headcured": [
                                "headp"
                            ],
                            "lightcured": [
                                "lightp"
                            ],
                            "thundercured": [
                                "thunderp"
                            ],
                            "light2cured": [
                                "light2p"
                            ],
                            "thunder2cured": [
                                "thunder2p"
                            ],
							"bombnightcured": [
								"bombnightp"
							],
							"bombdaycured": [
								"bombdayp"
							],
							"bombvotecured": [
								"bombvotep"
							],
							"villager3cured": [
								"villager3p"
							]
                        },
                        "charges": 2,
                        "silent": true
                    }
                }
            }
        },
		{
            "role": "infectorsmall",
            "translation": "Infector",
            "side": "mafia",
            "help": "You're  here to infiltrate and take over this village! However, within you lies  the mafia's secret weapon: a deadly virus. Since you're already  infected with it, your goal is to infect someone else in order to spread  the virus. Use /infect to  infect someone; this will convert them into an infected role!  As a bonus, you can't be stalked and you can /kill during the night, but you can only do this once!(Use /tt to talk to your teammates.)",
            "info": "Can kill one person during the night once per game. Can infect (poison) one person during the night (infected people can spread the poison using /infect). Ignores stalk. Sided with the Outbreak.",
            "actions": {
                "preventTeamvote": true,
				"startup": "team-reveal-with-roles",
                "teamTalk": true,
                "night": {
                    "kill": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 14,
						"broadcast": "team",
						"charges": 1,
						"hide": true
					},
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 28,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "stalk": {
                    "mode": "noVisit"
                }
            }
        },
		{
            "role": "infectorsmallp",
            "translation": "Infector",
            "side": "mafia",
			"hide": true,
            "help": "Looks like you've been infected with the virus and will die the next night. You can still /infect one person before going down! If you saved it, you can /kill one person as well.",
            "info": "Can infect (poison) one person during the night (infected people can spread the poison using /infect). Ignores stalk. Sided with the Outbreak.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "night": {
                    "kill": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 14,
						"broadcast": "team",
						"hide": true
					},
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 28,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "stalk": {
                    "mode": "noVisit"
                }
            }
        },
        {
            "role": "infector",
            "translation": "Infector",
            "side": "mafia",
            "help": "You're  here to infiltrate and take over this village! However, within you lies  the mafia's secret weapon: a deadly virus. Since you're already  infected with it, your goal is to infect someone else in order to spread  the virus. This also means you can't be poisoned. Use /infect to  infect someone; this will convert them into an infected role!  Use /kill  during  the night to eliminate someone (shared with your teammates)!  As a bonus, you can't be stalked and you have a 50% chance to evade nightkills. (Use /tt to talk to your teammates.)",
            "info": "Can infect (poison) one person during the night (infected people can spread the poison using /infect). Can kill one person during the night. Ignores stalk. Has a 50% chance to evade nightkills. Can't be poisoned. Sided with the Outbreak.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 28,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Infector) has decided to infect ~Target~!",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
						"hide": true,
                        "broadcast": "team"
                    }
                },
                "stalk": {
                    "mode": "noVisit"
                },
				"kill": {
					"mode": {
						"evadeChance": 0.5
					}
				}
            }
        },
        {
            "role": "infectorcured",
            "translation": "Infector",
            "side": "mafia",
			"hide": true,
            "help": "You have been cured and live to see another day! You're  here to infiltrate and take over this village! However, within you lies  the mafia's secret weapon: a deadly virus. Since you're already  infected with it, your goal is to infect someone else in order to spread  the virus. Use /infect to  infect someone; this will convert them into an infected role!  Use /kill  during  the night to eliminate someone (shared with your teammates)!  As a bonus, you can't be stalked and have a 50% chance to evade nightkills. (Use /tt to talk to your teammates.)",
            "info": "Can infect (poison) one person during the night. Can kill someoend uring the night (shared with team). Sided with the Outbreak.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 28,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Infector) has decided to infect ~Target~!",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
						"hide": true
                    }
                },
                "stalk": {
                    "mode": "noVisit"
                },
				"kill": {
					"mode": {
						"evadeChance": 0.5
					}
				}
            }
        },
        {
            "role": "infectorp",
            "translation": "Infector",
            "side": "mafia",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! You're here to infiltrate and take over this village!  However, within you lies the mafia's secret weapon: a deadly virus.  Since you're already infected with it, your goal is to infect someone  else in order to spread the virus.  Use /infect to infect someone; this will convert them into an  infected role! Use /kill during  the night to eliminate someone (shared  with your teammates)! As a bonus, you can't be stalked and have a 50% chance to evade nightkills. (Use /tt to talk to your teammates.)",
            "info": "Can infect (poison) one person during the night. Can kill someone during the night (shared). Sided with the Outbreak.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 28,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Infector) has decided to infect ~Target~!",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    }
                },
                "stalk": {
                    "mode": "noVisit"
                },
				"kill": {
					"mode": {
						"evadeChance": 0.5
					}
				}
            }
        },
        {
            "role": "savage",
            "translation": "Savage",
            "side": "mafia",
            "help": "A product of an experiment gone horribly wrong, you suffer from violent impulses that allow you to /kill one person at night. If anyone comes too close to you (tries to protect you or distract you), you will kill them instead!",
            "info": "Can kill one person during the night. Kills distractors and protectors. Sided with the Outbreak.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "distract": {
                    "mode": "ChangeTarget",
                    "hookermsg": "You tried to get in the way of a savage? That wasn't very smart...and now you're dead.",
                    "msg": "Someone tried to stop you last night. You simply ripped them apart instead."
                },
                "protect": {
                    "mode": "killattackerevenifprotected",
                    "msg": "Your intentions were good, but you got way too close to the savage. It simply lunged at you and ripped you to shreds."
                }
            }
        },
        {
            "role": "savagecured",
            "translation": "Savage",
            "side": "mafia",
			"hide": true,
            "help": "You have been cured and live to see another day! A product of an experiment gone horribly wrong, you suffer from violent impulses that allow you to /kill one person at night. If anyone comes too close to you (tries to protect you or distract you), you will kill them instead!",
            "info": "Can kill (shared with team) one person during the night. If anyone protects/distracts it, they die. Sided with the Outbreak.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "distract": {
                    "mode": "ChangeTarget",
                    "hookermsg": "You tried to get in the way of a savage? That wasn't very smart...and now you're dead.",
                    "msg": "Someone tried to stop you last night. You simply ripped them apart instead."
                },
                "protect": {
                    "mode": "killattackerevenifprotected",
                    "msg": "Your intentions were good, but you got way too close to the savage. It simply lunged at you and ripped you to shreds."
                }
            }
        },
        {
            "role": "savagep",
            "translation": "Savage",
            "side": "mafia",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! A product of an experiment gone horribly wrong, you suffer from violent impulses that allow you to /kill one person at night. If anyone comes too close to you (tries to protect you or distract you), you will kill them instead!",
            "info": "Can kill (shared with team) one person during the night. If anyone protects/distracts it, they die. Sided with the Outbreak.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 14,
                        "broadcast": "team",
                        "hide": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
                "distract": {
                    "mode": "ChangeTarget",
                    "hookermsg": "You tried to get in the way of a savage? That wasn't very smart...and now you're dead.",
                    "msg": "Someone tried to stop you last night. You simply ripped them apart instead."
                },
                "protect": {
                    "mode": "killattackerevenifprotected",
                    "msg": "Your intentions were good, but you got way too close to the savage. It simply lunged at you and ripped you to shreds."
                }
            }
        },
		{
			"role": "outbreak_prio",
			"translation": "Outbreak",
			"side": "alien",
			"help": "Placeholder role for /priority formatting",
			"hide": true,
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 14,
						"broadcast": "team"
					}
				}
			}
		},
        {
            "role": "meth",
            "translation": "Meth Dealer",
            "side": "druggies",
            "help": "A shady character specializing in the distribution of meth, your only goal is to make money off of this. In order to do that, you need to eliminate any potential competition or threat to your business. You can do this by using /kill each night, which is shared with your team. You can also give meth to someone by using /meth; this will distract that person.",
            "info": "Can kill one person during the night. Can meth (distract) one person during the night. Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "meth": {
                        "command": "distract",
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 4,
                        "distractmsg": "You weren't able to do anything during the night as you  were having fun getting high from meth.",
                        "teammsg": "Your partner was completely out of it because he was getting high on the meth that the dealer gave to them."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "methcured",
            "translation": "Meth Dealer",
            "side": "druggies",
			"hide": true,
            "help": "You have been cured and live to see another day! A shady character specializing in the distribution of meth, your only goal is to make money off of this. In order to do that, you need to eliminate any potential competition or threat to your business. You can do this by using /kill each night, which is shared with your team. You can also give meth to someone by using /meth; this will distract that person.",
            "info": "Can kill one person during the night. Can meth (distract) one person during the night. Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "meth": {
                        "command": "distract",
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 4,
                        "distractmsg": "You weren't able to do anything during the night as you  were having fun getting high from meth.",
                        "teammsg": "Your partner was completely out of it because he was getting high on the meth that the dealer gave to them."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "methp",
            "translation": "Meth Dealer",
            "side": "druggies",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! A shady character specializing in the distribution of meth, your only goal is to make money off of this. In order to do that, you need to eliminate any potential competition or threat to your business. You can do this by using /kill each night, which is shared with your team. You can also give meth to someone by using /meth; this will distract that person.",
            "info": "Can kill one person during the night. Can meth (distract) one person during the night. Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    },
                    "meth": {
                        "command": "distract",
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 4,
                        "distractmsg": "You weren't able to do anything during the night as you  were having fun getting high from meth.",
                        "teammsg": "Your partner was completely out of it because he was getting high on the meth that the dealer gave to them."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alcohol",
            "translation": "Alcoholic",
            "side": "druggies",
            "help": "You've lived a troubled life thanks to your addiction to alcohol, and it doesn't look like it will be improving any time soon. Your clouded mind and judgment allow you to recklessly /kill one person at night (shared among your team). Your recklessness causes you to be bold, thus allowing you to /protect one of your teammates every night.",
            "info": "Can kill one person during the night. Can protect one person during the night. Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 8,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Alcoholic) has decided to protect ~Target~!"
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alcoholcured",
            "translation": "Alcoholic",
            "side": "druggies",
			"hide": true,
            "help": "You have been cured and live to see another day! You've lived a troubled life thanks to your addiction to alcohol, and it doesn't look like it will be improving any time soon. Your clouded mind and judgment allow you to recklessly /kill one person at night (shared among your team). Your recklessness causes you to be bold, thus allowing you to /protect one of your teammates every night.",
            "info": "Can protect one of its teammates during the night, and also nightkill (shared with its team). Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 8,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Alcoholic) has decided to protect ~Target~!"
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alcoholp",
            "translation": "Alcoholic",
            "side": "druggies",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! You've lived a troubled life thanks to your addiction to alcohol, and it doesn't look like it will be improving any time soon. Your clouded mind and judgment allow you to recklessly /kill one person at night (shared among your team). Your recklessness causes you to be bold, thus allowing you to /protect one of your teammates every night.",
            "info": "Can protect one of its teammates during the night, and also nightkill (shared with its team). Sided with the Drug Dealers.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 8,
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Alcoholic) has decided to protect ~Target~!"
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "heroin",
            "translation": "Heroin Addict",
            "side": "druggies",
            "help": "Your addiction has driven you down a path of despair and danger, so you've been forced to take drastic measures to survive. You can /kill one person at night (shared among your team). You can also /expose someone's role during the day, but due to your hallucinations, you can fake expose someone instead. Additionally, since you refuse to be taken down, you will be able to kill one more person before dying if you are lynched!",
            "info": "Can kill one person during the night. Can expose or fake-expose someone as Civilian, Detective, UFO, Infector, Alien Mesmerizer, or Police Officer. If lynched, can kill one person during the night (outspeeding bodyguards and distractors) before dying. Sided with the Drug Dealers.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
				"lynch": {
                    "convertTo": "heroin2",
                    "convertmsg": "±~Self~: 'I feel the rush! I've never felt so alive! More! Moooooooore!' (~Self~ can kill one more person before dying!)"
                },
                "standby": {
                    "expose": {
                        "target": "AnyButTeam",
                        "msg": "You can use /expose now to reveal someone's role to everyone!",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a ~Role~!"
                    },
                    "civilian": {
                        "command": "expose",
                        "target": "Any",
                        "msg": "Or, you can use /civilian, /detective, /ufo, /infector, /mesmerizer, or /police to fake expose someone (or yourself) as being one of these roles.",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Civilian!"
                    },
                    "detective": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Detective!"
                    },
                    "ufo": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a UFO!"
                    },
                    "infector": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Infector!"
                    },
                    "mesmerizer": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Alien Mesmerizer!"
                    },
                    "police": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Police Officer!"
                    }
                },
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    }
                }
            }
        },
        {
            "role": "heroincured",
            "translation": "Heroin Addict",
            "side": "druggies",
			"hide": true,
            "help": "You have been cured and live to see another day! Your addiction has driven you down a path of despair and danger, so you've been forced to take drastic measures to survive. You can /kill one person at night (shared among your team). You can also /expose someone's role during the day, but due to your hallucinations, you can fake expose someone instead. Additionally, since you refuse to be taken down, you will be able to kill one more person before dying if you are lynched!",
            "info": "Can kill one person during the night. Can expose or fake-expose someone as Civilian, Detective, UFO, Infector, Alien Mesmerizer, or Police Officer. It can also kill during the night (shared with its team). If lynched, can kill one person during the night (outspeeding bodyguards and distractors) before dying. Sided with the Drug Dealers.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
				"lynch": {
                    "convertTo": "heroin2",
                    "convertmsg": "±~Self~: 'I feel the rush! I've never felt so alive! More! Moooooooore!' (~Self~ can kill one more person before dying!)"
                },
                "standby": {
                    "expose": {
                        "target": "AnyButTeam",
                        "msg": "You can use /expose now to reveal someone's role to everyone!",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a ~Role~!"
                    },
                    "civilian": {
                        "command": "expose",
                        "target": "Any",
                        "msg": "Or, you can use /civilian, /detective, /ufo, /infector, /mesmerizer, or /police to fake expose someone (or yourself) as being one of these roles.",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Civilian!"
                    },
                    "detective": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Detective!"
                    },
                    "ufo": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a UFO!"
                    },
                    "infector": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Infector!"
                    },
                    "mesmerizer": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Alien Mesmerizer!"
                    },
                    "police": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Police Officer!"
                    }
                },
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    }
                }
            }
        },
        {
            "role": "heroinp",
            "translation": "Heroin Addict",
            "side": "druggies",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! Your addiction has driven you down a path of despair and danger, so you've been forced to take drastic measures to survive. You can /kill one person at night (shared among your team). You can also /expose someone's role during the day, but due to your hallucinations, you can fake expose someone instead. Additionally, since you refuse to be taken down, you will be able to kill one more person before dying if you are lynched!",
            "info": "Can kill one person during the night. Can expose or fake-expose someone as Civilian, Detective, UFO, Infector, Alien Mesmerizer, or Police Officer. It can also kill during the night (shared with its team). If lynched, can kill one person during the night (outspeeding bodyguards and distractors) before dying. Sided with the Drug Dealers.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
				"lynch": {
                    "convertTo": "heroin2p",
                    "convertmsg": "±~Self~: 'I feel the rush! I've never felt so alive! More! Moooooooore!' (~Self~ can kill one more person before dying!)"
                },
                "standby": {
                    "expose": {
                        "target": "AnyButTeam",
                        "msg": "You can use /expose now to reveal someone's role to everyone!",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a ~Role~!"
                    },
                    "civilian": {
                        "command": "expose",
                        "target": "Any",
                        "msg": "Or, you can use /civilian, /detective, /ufo, /infector, /mesmerizer, or /police to fake expose someone (or yourself) as being one of these roles.",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Civilian!"
                    },
                    "detective": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Detective!"
                    },
                    "ufo": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a UFO!"
                    },
                    "infector": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Infector!"
                    },
                    "mesmerizer": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Alien Mesmerizer!"
                    },
                    "police": {
                        "command": "expose",
                        "target": "Any",
                        "exposemsg": "The voices...they speak to me...they tell me that ~Target~ is indeed a Police Officer!"
                    }
                },
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 15
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                }
            }
        },
		{
            "role": "heroin2",
            "translation": "Heroin Addict",
            "side": "druggies",
			"hide": true,
            "help": "CAN YOU FEEL THE RUSH?! OF COURSE YOU CAN! Before you die, you will be able to kill someone using /smash! This kill outspeeds bodyguards and distractors, so it can't be stopped!",
            "info": "Can kill one person during the night. Can expose or fake-expose someone as Civilian, Meth Dealer, Lightning, Chieftain, Thunder, Infector, Alien Mesmerizer, or Police Officer. If lynched, can kill one person during the night (outspeeding bodyguards and distractors) before dying. Sided with the Drug Dealers.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,				
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
				"detox": {
					"mode": "ignore"
				},
				"distract": {
					"mode": "ignore",
					"msg": "The ~Distracter~ came to you last night! How foolish of them, as you already made your kill!"
				},
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "The rush is over. The side effects have kicked in and are too much. You had your fun, so you can now peacefully die."
                    }
                },
				"night": {                    
					"smash": {
						"command": "kill",
						"target": "AnyButTeam",
						"common": "Self",
						"restrict": ["smash"],
						"broadcast": "*",
						"broadcastmsg": "*** The Heroin Addict has chosen to smash ~Target~! (This kill is guaranteed!)",
						"priority": 2
					}
                }
            }
        },
		{
            "role": "heroin2p",
            "translation": "Heroin Addict",
            "side": "druggies",
			"hide": true,
            "help": "CAN YOU FEEL THE RUSH?! OF COURSE YOU CAN! Before you die, you will be able to kill someone using /smash! This kill outspeeds bodyguards and distractors, so it can't be stopped! Don't forget that you can also /infect someone to spread the virus!",
            "info": "Can kill one person during the night. Can expose or fake-expose someone as Civilian, Meth Dealer, Lightning, Chieftain, Thunder, Infector, Alien Mesmerizer, or Police Officer. If lynched, can kill one person during the night (outspeeding bodyguards and distractors) before dying. Sided with the Drug Dealers.",
            "actions": {
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,				
                "convert": {
                    "mode": "ignore"
                },
                "kill": {
                    "mode": "ignore"
                },
				"detox": {
					"mode": "ignore"
				},
				"distract": {
					"mode": "ignore",
					"msg": "The ~Distracter~ came to you last night! How foolish of them, as you already made your kill!"
				},
                "initialCondition": {
                    "poison": {
                        "count": -1,
                        "poisonDeadMessage": "The rush is over. The side effects have kicked in and are too much. You had your fun, so you can now peacefully die."
                    }
                },
				"night": {                    
					"smash": {
						"command": "kill",
						"target": "AnyButTeam",
						"common": "Self",
						"restrict": ["smash"],
						"broadcast": "*",
						"broadcastmsg": "*** The Heroin Addict has chosen to smash ~Target~! (This kill is guaranteed!)",
						"priority": 2,
						"hide": true
					},
					"infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                }
            }
        },
		{
			"role": "druggies_prio",
			"translation": "Drug Dealers",
			"side": "druggies",
			"help": "Placeholder role for /priority formatting",
			"hide": true,
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 15,
						"broadcast": "team"
					}
				}
			}
		},
        {
            "role": "alien",
            "translation": "Alien",
            "side": "alien",
            "help": "You've come in an attempt to take over this place! To achieve this goal, you are able to /kill one person during the night. You also have a decent chance to hax bodyguards and distractors.",
            "info": "Can kill one person during the night. Gets medium hax on protect and distract. Sided with the Aliens.",
            "actions": {
                "hax": {
                    "protect": {
                        "revealTeam": 0.3,
						"revealPlayer": 0.3
                    },
					"distract": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					},
					"meth": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					}
				},
				"night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "aliencured",
            "translation": "Alien",
            "side": "alien",
			"hide": true,
            "help": "You have been cured and live to see another day! You've come in an attempt to take over this place! To achieve this goal, you are able to /kill one person during the night. You also have a decent chance to hax bodyguards and distractors.",
            "info": "Can kill 1 person during the night (shared with its team). Sided with the Aliens.",
            "actions": {
                "hax": {
                    "protect": {
                        "revealTeam": 0.3,
						"revealPlayer": 0.3
                    },
					"distract": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					},
					"meth": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					}
				},
				"night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alienp",
            "translation": "Alien",
            "side": "alien",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! You've come in an attempt to take over this place! To achieve this goal, you are able to /kill one person during the night. You also have a decent chance to hax bodyguards and distractors.",
            "info": "Can kill 1 person during the night (shared with its team). Sided with the Aliens.",
            "actions": {
                "hax": {
                    "protect": {
                        "revealTeam": 0.3,
						"revealPlayer": 0.3
                    },
					"distract": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					},
					"meth": {
						"revealTeam": 0.3,
						"revealPlayer": 0.3
					}
				},
				"night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
		{
            "role": "ufostrong",
            "translation": "UFO",
            "side": "alien",
			"hide": "side",
            "help": "You are the means of transportation for the aliens! While you can't kill at night, you are able to abduct someone using /transport during the day to get rid of them! This won't reveal you either! Your sturdy structure prevents you from being poisoned and you are able to survive one nightkill!",
            "info": "Can transport (kill) one person during the day (user is not revealed). Can't be poisoned. Evades 1 nightkill. Sided with the Aliens.",
            "actions": {
                "standby": {
                    "transport": {
                        "command": "kill",
                        "msg": "Look at everyone in panic and turmoil! This is the perfect time to /transport someone to remove them! This won't reveal you, so you are safe to do this every day!",
                        "target": "AnyButTeam",
                        "killmsg": "A UFO has been spotted! Everyone watches in awe as it swoops down towards ~Target~, and sucks them in before flying off, never to be seen again."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"kill": {
					"mode": {
						"evadeCharges": 1
					},
					"evadechargemsg": "Your sturdy structure allowed you to survive an attack!",
					"msg": "Your target appears to be quite sturdy. It looks like you will need to hit them one more time to bring them down."
				},				
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "ufo",
            "translation": "UFO",
            "side": "alien",
            "help": "You are the means of transportation for the aliens! While you can't kill at night, you are able to abduct someone using /transport during the day to get rid of them! This won't reveal you either! Your sturdy structure prevents you from being poisoned as well.",
            "info": "Can transport (kill) one person during the day (user is not revealed). Can't be poisoned. Sided with the Aliens.",
            "actions": {
                "standby": {
                    "transport": {
                        "command": "kill",
                        "msg": "Look at everyone in panic and turmoil! This is the perfect time to /transport someone to remove them! This won't reveal you, so you are safe to do this every day!",
                        "target": "AnyButTeam",
                        "killmsg": "A UFO has been spotted! Everyone watches in awe as it swoops down towards ~Target~, and sucks them in before flying off, never to be seen again."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "ufocured",
            "translation": "UFO",
            "side": "alien",
			"hide": true,
            "help": "You have been cured and live to see another day! You are the means of transportation for the aliens! While you can't kill at night, you are able to abduct someone using /transport during the day to get rid of them! This won't reveal you either! Your sturdy structure prevents you from being poisoned as well.",
            "info": "Can transport (kill) one person during the day (user is not revealed). Sided with the Aliens.",
            "actions": {
                "standby": {
                    "transport": {
                        "command": "kill",
                        "msg": "Look at everyone in panic and turmoil! This is the perfect time to /transport someone to remove them! This won't reveal you, so you are safe to do this every day!",
                        "target": "AnyButTeam",
                        "killmsg": "A UFO has been spotted! Everyone watches in awe as it swoops down towards ~Target~, and sucks them in before flying off, never to be seen again."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "ufop",
            "translation": "UFO",
            "side": "alien",
			"hide": true,
            "help": "THIS IS JUST FILLER STUFF TO PREVENT ERRORS. THIS ROLE DOES NOT ACTUALLY EXIST. You are the means of transportation for the aliens! While you can't kill at night, you are able to abduct someone using /transport during the day to get rid of them! This won't reveal you either! Your sturdy structure prevents you from being poisoned as well.",
            "info": "Can transport (kill) one person during the day (user is not revealed). Sided with the Aliens.",
            "actions": {
                "standby": {
                    "transport": {
                        "command": "kill",
                        "msg": "Look at everyone in panic and turmoil! This is the perfect time to /transport someone to remove them! This won't reveal you, so you are safe to do this every day!",
                        "target": "AnyButTeam",
                        "killmsg": "A UFO has been spotted! Everyone watches in awe as it swoops down towards ~Target~, and sucks them in before flying off, never to be seen again."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alienm",
            "translation": "Alien Mesmerizer",
            "side": "alien",
            "help": "You are a very strange alien looking to enslave everyone here! Your odd design and features allow you to /distract one person during the night, and you share a /kill every night with your teammates. Additionally, you can /inspect one person to find out what their role is!",
            "info": "Can kill one person during the night. Can distract one person during the night. Can inspect one person during the night. Sided with the Aliens.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    },
                    "distract": {
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 3,
                        "distractmsg": "AN ALIEN! Woah, this one looks a little odd. You spent the entire night observing it and didn't perform any of your nightly duties.",
                        "teammsg": "You were unable to do anything as you spent the night trying to get your teammate to focus on their job. It seems as if they saw an alien."
                    },
					"inspect": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 20,
						"broadcast": "team"
					}
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alienmcured",
            "translation": "Alien Mesmerizer",
            "side": "alien",
			"hide": true,
            "help": "You have been cured and live to see another day! You are a very strange alien looking to enslave everyone here! Your odd design and features allow you to /distract one person during the night, and you share a /kill every night with your teammates. Additionally, you can /inspect one person to find out what their role is!",
            "info": "Can distract someone during the night, and kill (shared with their team) during the night. Can inspect one person during the night (reveals side). Sided with the Aliens.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    },
                    "distract": {
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 3,
                        "distractmsg": "AN ALIEN! Woah, this one looks a little odd. You spent the entire night observing it and didn't perform any of your nightly duties.",
                        "teammsg": "You were unable to do anything as you spent the night trying to get your teammate to focus on their job. It seems as if they saw an alien."
                    },
					"inspect": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 20,
						"broadcast": "team"
					}
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "alienmp",
            "translation": "Alien Mesmerizer",
            "side": "alien",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! You are a very strange alien looking to enslave everyone here! Your odd design and features allow you to /distract one person during the night, and you share a /kill every night with your teammates. Additionally, you can /inspect one person to find out what their role is!",
            "info": "Can distract someone during the night, and kill (shared with their team) during the night. Can inspect one person during the night (reveals side). Sided with the Aliens.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "broadcast": "team",
						"hide": true,
                        "priority": 12
                    },
                    "distract": {
                        "target": "AnyButTeam",
                        "common": "Self",
						"broadcast": "team",
                        "priority": 3,
                        "distractmsg": "AN ALIEN! Woah, this one looks a little odd. You spent the entire night observing it and didn't perform any of your nightly duties.",
                        "teammsg": "You were unable to do anything as you spent the night trying to get your teammate to focus on their job. It seems as if they saw an alien."
                    },
					"inspect": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 20,
						"broadcast": "team"
					},
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
		{
			"role": "alien_prio",
			"translation": "Aliens",
			"side": "alien",
			"help": "Placeholder role for /priority formatting",
			"hide": true,
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 12,
						"broadcast": "team"
					}
				}
			}
		},
        {
            "role": "indian",
            "translation": "Indian",
            "side": "indian",
            "help": "It seems like there has been a disturbance on your land. You must keep everyone else off your land. Defend your territory by using /kill to kill any intruder! This kill is shared among your team.",
            "info": "Can kill one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
                        "broadcast": "team",
						"hide": true
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "indiancured",
            "translation": "Indian",
            "side": "indian",
			"hide": true,
            "help": "You have been cured and live to see another day! It seems like there has been a disturbance on your land. You must keep everyone else off your land. Defend your territory by using /kill to kill any intruder! This kill is shared among your team.",
            "info": "Can kill one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
                        "broadcast": "team",
						"hide": true
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "indianp",
            "translation": "Indian",
            "side": "indian",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! It seems like there has been a disturbance on your land. You must keep everyone else off your land. Defend your territory by using /kill to kill any intruder! This kill is shared among your team.",
            "info": "Can kill one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
                        "broadcast": "team",
						"hide": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "chiefstrong",
            "translation": "Chieftain",
            "side": "indian",
			"hide": "side",
            "help": "As the head of your tribe, you must defend your land at all costs! You can /kill one person every night! You can also /ambush someone to kill them; this kill bypasses protect, but you can only use it once a game. You are able to /follow one person as well to find out who they visited! Lastly, your strong will allows you to survive one nightkill and you can't be distracted!",
            "info": "Can kill one person during the night. Can ambush (kill) one person during the night (bypasses protect) once a game. Can follow (stalk) one person during the night. Ignores all distractors. Evades 1 nightkill. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "ambush": {
                        "command": "kill",
						"target": "AnyButTeam",
                        "common": "Self",
                        "priority": 13,
                        "broadcast": "team",
						"pierce": true,
						"charges": 1
                    }
				},
				"distract": {
					"mode": "ignore"
				},
				"kill": {
					"mode": {
						"evadeCharges": 1
					},
					"evadechargemsg": "Your strong will allowed you to survive an attack!",
					"msg": "Your target has somehow survived your attack. It looks like you will need to hit them one more time to bring them down."
				},
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "chiefstrongcured",
            "translation": "Chieftain",
            "side": "indian",
			"hide": true,
            "help": "You have been cured and live to see another day! As the head of your tribe, you must defend your land at all costs! You can /kill one person every night! You can also /ambush someone to kill them; this kill bypasses protect, but you can only use it once a game. You are able to /follow one person as well to find out who they visited! Lastly, your strong will allows you to survive one nightkill and you can't be distracted!",
            "info": "Can kill one person during the night. Can ambush (kill) one person during the night (bypasses protect) once a game. Can follow (stalk) one person during the night. Ignores all distractors. Evades 1 nightkill. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "ambush": {
                        "command": "kill",
						"target": "AnyButTeam",
                        "common": "Self",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team",
						"pierce": true
                    }
				},
				"distract": {
					"mode": "ignore"
				},
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "chiefstrongp",
            "translation": "Chieftain",
            "side": "indian",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! As the head of your tribe, you must defend your land at all costs! You can /kill one person every night! You can also /ambush someone to kill them; this kill bypasses protect, but you can only use it once a game. You are able to /follow one person as well to find out who they visited! Lastly, your strong will allows you to survive one nightkill and you can't be distracted!",
            "info": "Can kill one person during the night. Can ambush (kill) one person during the night (bypasses protect) once a game. Can follow (stalk) one person during the night. Ignores all distractors. Evades 1 nightkill. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "ambush": {
                        "command": "kill",
						"target": "AnyButTeam",
                        "common": "Self",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team",
						"pierce": true
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
		{
            "role": "chief",
            "translation": "Chieftain",
            "side": "indian",
            "help": "As the head of your tribe, you must defend your land at all costs! You share a /kill at night with your team. You are able to /follow one person as well to find out who they visited! Lastly, as a leader, you value the lives of your teammates, so you can also /protect one of them during the night.",
            "info": "Can kill one person during the night. Can follow (stalk) one person during the night. Can protect one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 10,
                        "broadcast": "team"
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "chiefcured",
            "translation": "Chieftain",
            "side": "indian",
			"hide": true,
            "help": "You have been cured and live to see another day! As the head of your tribe, you must defend your land at all costs! You share a /kill at night with your team. You are able to /follow one person as well to find out who they visited! Lastly, as a leader, you value the lives of your teammates, so you can also /protect one of them during the night.",
            "info": "Can kill one person during the night. Can follow (stalk) one person during the night. Can protect one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 10,
                        "broadcast": "team"
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "chiefp",
            "translation": "Chieftain",
            "side": "indian",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! As the head of your tribe, you must defend your land at all costs! You share a /kill at night with your team. You are able to /follow one person as well to find out who they visited! Lastly, as a leader, you value the lives of your teammates, so you can also /protect one of them during the night.",
            "info": "Can kill one person during the night. Can follow (stalk) one person during the night. Can protect one person during the night. Sided with the Indians.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Team",
                        "priority": 13,
						"hide": true,
                        "broadcast": "team"
                    },
                    "follow": {
                        "command": "stalk",
                        "target": "AnyButTeam",
                        "common": "Self",
						"hide": true,
                        "priority": 25,
                        "broadcast": "team"
                    },
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 5,
                        "broadcast": "team"
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
        {
            "role": "head",
            "translation": "Head Shrinker",
            "side": "indian",
            "help": "You are known for shrinking heads. Since you shrink heads, you can use /shrink one person during the night, which will poison them and kill them after 3 nights. You can use this on two people every night. Since you are difficult to find, you also have a -2 voteshield.",
            "info": "Can shrink (poison) two people during the night, killing them after three nights. Voteshield of -2. Sided with the Indians.",
            "actions": {
                "night": {                    
                    "shrink": {
                        "command": "poison",
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 22,
                        "broadcast": "team",
                        "broadcastmsg": "Your teammate ~Player~ (Head Shrinker) has decided to poison ~Target~!",
                        "count": 3,
                        "limit": 2,
                        "poisonDeadMessage": "The Head Shrinker shrunk your head, and poisoned you. It took 3 days to shrink your head, but it has been shrunk. What a decorative head they have."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
				"voteshield": -2
            }
        },
        {
            "role": "headcured",
            "translation": "Head Shrinker",
            "side": "indian",
			"hide": true,
            "help": "You have been cured and live to see another day! You are known for shrinking heads. Since you shrink heads, you can use /shrink one person during the night, which will poison them and kill them after 3 nights. You can use this on two people every night. Since you are difficult to find, you also have a -2 voteshield.",
            "info": "Can shrink (poison) two people during the night, killing them after three nighs. Voteshield of -2. Sided with the Indians.",
            "actions": {
                "night": {                    
                    "shrink": {
                        "command": "poison",
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 22,
                        "broadcast": "team",
                        "broadcastmsg": "Your teammate ~Player~ (Head Shrinker) has decided to poison ~Target~!",
                        "count": 3,
                        "limit": 2,
                        "poisonDeadMessage": "The Head Shrinker shrunk your head, and poisoned you. It took 3 days to shrink your head, but it has been shrunk. What a decorative head they have."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true,
				"voteshield": -2
            }
        },
        {
            "role": "headp",
            "translation": "Head Shrinker",
            "side": "indian",
			"hide": true,
            "help": "You have been infected with the virus, and unless you're cured, you will die the next night! However, you yourself may spread the virus in hopes of infecting those not on your team using /infect, but you can only do this once! You are known for shrinking heads. Since you shrink heads, you can use /shrink one person during the night, which will poison them and kill them after 3 nights. You can use this on two people every night. Since you are difficult to find, you also have a -2 voteshield.",
            "info": "Can shrink (poison) two people during the night, killing them after three nighs. Voteshield of -2. Sided with the Indians.",
            "actions": {
                "voteshield": -2,
				"night": {                    
                    "shrink": {
                        "command": "poison",
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 22,
                        "broadcast": "team",
                        "broadcastmsg": "Your teammate ~Player~ (Head Shrinker) has decided to poison ~Target~!",
                        "count": 3,
                        "limit": 2,
                        "poisonDeadMessage": "The Head Shrinker shrunk your head, and poisoned  you. It took 3 days to shrink your head, but it has been shrunk. What a  decorative head they have."
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
				"preventTeamvote": true,
                "teamTalk": true
            }
        },
		{
			"role": "indian_prio",
			"translation": "Indians",
			"side": "indian",
			"help": "Placeholder role for /priority formatting",
			"hide": true,
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 13,
						"broadcast": "team"
					}
				}
			}
		},
        {
            "role": "light",
            "translation": "Lightning",
            "side": "nature",
            "help": "A  powerful discharge from clouds, you thrive in thunderstorms. However,  you have to wait for the rain to fall and the storm clouds to form  before you can strike. This means you won't be able to kill until the  4th night, but once that night comes, you can kill up to 2 people during  the night using /kill. Your blinding speed and power gives you a 30%  chance to evade nightkills, and you can't be poisoned. However, if Rain dies, the storm ceases, and  you therefore die with it.",
            "info": "Powers up after the 3rd night. Has a 30% chance to evade nightkills. Can't be poisoned. Sided with Nature.",
            "actions": {
                "initialCondition": {
                    "curse": {
                        "curseCount": 3,
                        "cursedRole": "light2",
                        "curseConvertMessage": "The heavy downpour begins. Now is the time for lightning to strike...not once, not twice, but three times a night."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"kill": {
                    "mode": {
                        "evadeChance": 0.3
                    }
                },
                "startup": {
					"revealRole": [
						"light",
						"light2",
						"thunder",
						"thunder2"
					]
				},
                "teamTalk": [
					"light",
					"light2",
					"thunder",
					"thunder2"
				]
            }
        },
        {
            "role": "lightcured",
            "translation": "Lightning",
            "side": "nature",
			"hide": true,
            "help": "You have been cured and live to see another day! A  powerful discharge from clouds, you thrive in thunderstorms. However,  you have to wait for the rain to fall and the storm clouds to form  before you can strike. This means you won't be able to kill until the  4th night, but once that night comes, you can kill up to 2 people during  the night using /kill. Your blinding speed and power gives you a 30%  chance to evade nightkills. However, if Rain dies, the storm ceases, and  you therefore die with it.",
            "info": "Powers up after the 3rd night. Has a 30% chance to evade nightkills. Sided with Nature.",
            "actions": {
                "kill": {
                    "mode": {
                        "evadeChance": 0.3
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "lightp",
            "translation": "Lightning",
            "side": "nature",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! However, you yourself may spread the virus in hopes  of infecting those not on your team using /infect, but you can only do  this once! A powerful discharge from clouds, you thrive in  thunderstorms. However, you have to wait for the rain to fall and the  storm clouds to form before you can strike. This means you won't be able  to kill until the 4th night, but once that night comes, you can kill up  to 2 people during the night using /kill. Your blinding speed and power  gives you a 30% chance to evade nightkills. However, if Rain dies, the  storm ceases, and you therefore die with it.",
            "info": "Powers up after the 3rd night. Has a 30% chance to evade nightkills. Sided with Nature.",
            "actions": {
                "night": {
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "kill": {
                    "mode": {
                        "evadeChance": 0.3
                    }
                },
                "startup": {
					"revealRole": [
						"light",
						"light2",
						"thunder",
						"thunder2"
					]
				},
                "teamTalk": [
					"light",
					"light2",
					"thunder",
					"thunder2"
				]
            }
        },
        {
            "role": "light2",
            "translation": "Lightning",
            "side": "nature",
            "help": "The thunderstorm is here, and it's time for you to strike! You can kill up to 2 people during  the night using /kill. You no longer evade nightkills though, but you still can't be poisoned, and you can't be haxed! However, if Rain dies, the storm ceases, and  you therefore die with it.",
            "info": "Can kill 2 people during the night. Can't be poisoned. Can't be detected by spies. Sided with Nature.",
            "actions": {
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"avoidHax": [
                    "kill"
                ],
				"night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 11,
                        "broadcast": "team",
                        "limit": 2
                    }
                },
                "startup": {
					"revealRole": [
						"light",
						"light2",
						"thunder",
						"thunder2"
					]
				},
                "teamTalk": [
					"light",
					"light2",
					"thunder",
					"thunder2"
				]
            }
        },
        {
            "role": "light2cured",
            "translation": "Lightning",
            "side": "nature",
			"hide": true,
            "help": "You have been cured and live to see another day! The thunderstorm is here, and it's time for you to strike! You can kill up to 2 people during  the night using /kill. You no longer evade nightkills though. However, if Rain dies, the storm ceases, and  you therefore die with it.",
            "info": "Can kill 2 people during the night. Sided with Nature.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 11,
                        "broadcast": "team",
                        "limit": 2
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "light2p",
            "translation": "Lightning",
            "side": "nature",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! However, you yourself may spread the virus in hopes  of infecting those not on your team using /infect, but you can only do  this once! The thunderstorm is here, and it's time for you to strike! You can kill up to 2 people during  the night using /kill. You no longer evade nightkills though. However, if Rain dies, the storm ceases, and  you therefore die with it.",
            "info": "Can kill 2 people during the night. Sided with Nature.",
            "actions": {
                "night": {
                    "kill": {
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 11,
                        "broadcast": "team",
                        "limit": 2
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "thunder",
            "translation": "Thunder",
            "side": "nature",
            "help": "A  powerful sound caused by lightning from clouds, you thrive in  thunderstorms. However, you have to wait for the rain to fall and the  storm clouds to form before you can strike. You are able to /protect an  ally during the night, and starting on the 4th day, you will be able to  /kill someone during the day without being revealed. However, if Rain  dies, the storm ceases, and you therefore die with it. Additionally,  since sound is so fast, you have a 50% chance to evade nightkills, and you can't be poisoned.",
            "info": "Can protect one person during the night. Has a 50% chance of evading nightkills. Can't be poisoned. Powers up after the 3rd night. Sided with Nature.",
            "actions": {
                "initialCondition": {
                    "curse": {
                        "curseCount": 3,
                        "cursedRole": "thunder2",
                        "curseConvertMessage": "The heavy downpour begins. Prepare for the roars of thunder..."
                    }
                },
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Thunder) has decided to protect ~Target~!",
                        "priority": 7
                    }
                },
                "kill": {
                    "mode": {
                        "evadeChance": 0.5
                    }
                },
                "startup": {
					"revealRole": [
						"light",
						"light2",
						"thunder",
						"thunder2"
					]
				},
                "teamTalk": [
					"light",
					"light2",
					"thunder",
					"thunder2"
				]
            }
        },
        {
            "role": "thundercured",
            "translation": "Thunder",
            "side": "nature",
			"hide": true,
            "help": "You have been cured and live to see another day! A  powerful sound caused by lightning from clouds, you thrive in  thunderstorms. However, you have to wait for the rain to fall and the  storm clouds to form before you can strike. You are able to /protect an  ally during the night, and starting on the 4th day, you will be able to  /kill someone during the day without being revealed. However, if Rain  dies, the storm ceases, and you therefore die with it. Additionally,  since sound is so fast, you have a 50% chance to evade nightkills.",
            "info": "Can  protect one person during the night. Has a 50% chance of evading nightkills. Powers up after the 3rd night. Sided with Nature.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"hide": true,
                        "priority": 7
                    }
                },
                "kill": {
                    "mode": {
                        "evadeChance": 0.5
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "thunderp",
            "translation": "Thunder",
            "side": "nature",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! However, you yourself may spread the virus in hopes  of infecting those not on your team using /infect, but you can only do  this once! A powerful sound caused by lightning from clouds, you thrive  in thunderstorms. However, you have to wait for the rain to fall and the  storm clouds to form before you can strike. You are able to /protect an  ally during the night, and starting on the 4th day, you will be able to  /kill someone during the day without being revealed. However, if Rain  dies, the storm ceases, and you therefore die with it. Additionally,  since sound is so fast, you have a 50% chance to evade nightkills.",
            "info": "Can  protect one person during the night. Has a 50% chance of evading nightkills. Powers up after the 3rd night. Sided with Nature.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"hide": true,
                        "priority": 7
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "kill": {
                    "mode": {
                        "evadeChance": 0.5
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "thunder2",
            "translation": "Thunder",
            "side": "nature",
            "help": "The thunderstorm is here and it's time for you to strike! You can /kill one person during the day without being revealed and you are able to /protect an ally during the night. However, if Rain  dies, the storm ceases, and you therefore die with it. Unfortunately, you can no longer evade nightkills, but you still can't be poisoned.",
            "info": "Can  protect one person during the night. Can kill one person during the standby (user is not revealed). Can't be poisoned. Sided with Nature.",
            "actions": {
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"broadcastmsg": "Your teammate ~Player~ (Thunder) has decided to protect ~Target~!",
                        "priority": 7
                    }
                },
                "standby": {
                    "kill": {
                        "target": "AnyButTeam",
                        "killmsg": "As  the downpour continues, rumbles of thunder are heard across the sky.  Suddenly, a loud crackle of thunder is heard by ~Target~, paralyzing  them in their place. A large bolt of lightning strikes them, instantly  killing them and leaving nothing in their place."
                    }
                },
                "startup": {
					"revealRole": [
						"light",
						"light2",
						"thunder",
						"thunder2"
					]
				},
                "teamTalk": [
					"light",
					"light2",
					"thunder",
					"thunder2"
				]
            }
        },
        {
            "role": "thunder2cured",
            "translation": "Thunder",
            "side": "nature",
			"hide": true,
            "help": "You have been cured and live to see another day! The thunderstorm is here and it's time for you to strike! You can /kill one person during the day without being revealed and you are able to /protect an ally during the night. However, if Rain  dies, the storm ceases, and you therefore die with it. Unfortunately, you can no longer evade nightkills.",
            "info": "Can  protect one person during the night. Can kill one person during the standby (user is not revealed). Sided with Nature.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"hide": true,
                        "priority": 7
                    }
                },
                "standby": {
                    "kill": {
                        "target": "AnyButTeam",
                        "killmsg": "As  the downpour continues, rumbles of thunder are heard across the sky.  Suddenly, a loud crackle of thunder is heard by ~Target~, paralyzing  them in their place. A large bolt of lightning strikes them, instantly  killing them and leaving nothing in their place."
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "thunder2p",
            "translation": "Thunder",
            "side": "nature",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! However, you yourself may spread the virus in hopes  of infecting those not on your team using /infect, but you can only do  this once! The thunderstorm is here and it's time for you to strike! You can /kill one person during the day without being revealed and you are able to /protect an ally during the night. However, if Rain  dies, the storm ceases, and you therefore die with it. Unfortunately, you can no longer evade nightkills.",
            "info": "Can  protect one person during the night. Can kill one person during the day (user is not revealed). Sided with Nature.",
            "actions": {
                "night": {
                    "protect": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "broadcast": "team",
						"hide": true,
                        "priority": 5
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "standby": {
                    "kill": {
                        "target": "AnyButTeam",
                        "killmsg": "As  the downpour continues, rumbles of thunder are heard across the sky.  Suddenly, a loud crackle of thunder is heard by ~Target~, paralyzing  them in their place. A large bolt of lightning strikes them, instantly  killing them and leaving nothing in their place."
                    }
                },
                "startup": "team-reveal-with-roles",
                "teamTalk": true
            }
        },
        {
            "role": "rain",
            "translation": "Rain",
            "side": "nature",
            "help": "Drip  drip drop. You are the symbol of nature's tears. You have the ability  to /safeguard one person during the night. During the day, you can  /expose someone to rain down on them and determine their role (their  role will be revealed only to you). Since you are the medium for Thunder  and Lightning, if you die, they will die with you. You are the sacred weapon to your team, so you have a 1.1 vote and you can't be poisoned. If you are the last of your team, you will power up significantly.",
            "info": "Can safeguard one person during the night. Can expose (inspect) one person during the standby. Vote of 1.1. Kills Thunder and Lightning on death or on lynch. Can't be poisoned. Doesn't know its teammates. Converts into Hurricane if all teammates are dead. Sided with Nature.",
            "actions": {
                "poison": {
                    "mode": "ignore"
                },
                "convert": {
                    "mode": "ignore"
                },
				"standby": {
                    "expose": {
                        "target": "AnyButSelf",
                        "msg": "You can type /expose [name] to find out someone's role! This will only be revealed to you.",
                        "exposedtargetmsg": "You landed on ~Target~ and they shook you off, so you found out they were a ~Role~.",
                        "exposemsg": "The rain started to fall harder and everyone felt a chill go down their spines."
                    }
                },
                "night": {
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 1
                    }
                },
                "vote": 1.1,
                "onDeath": {
                    "killRoles": [
                        "light",
                        "thunder",
                        "light2",
                        "thunder2"
                    ]
                },
				"onDeadRoles": {
					"convertTo": {
						"hurricane": ["light", "light2", "thunder", "thunder2"]
					},
					"convertmsg": "Both the thunder and lightning have ceased, but the storm has just begun. Rain begins to fall at an alarmingly rapid rate as the winds pick up siginificant speed. A hurricane has developed."
				}
            }
        },		
        {
			"role": "hurricane",
			"translation": "Hurricane",
			"side": "nature",
			"players": "When both Thunder and Lightning die.",
			"help": "The true storm begins now! It's time to demonstrate Mother Nature's true power! Without any teammates, you can no longer /safeguard anyone. However, your vote has been increased to 500, so anyone you vote for will be lynched! In addition to that, you can /gust someone during the day to inspect them and find out their role (this will be revealed only to you)! You can also /flood someone to kill them during the day without being revealed! Lastly, you are still immune to poison.",
			"info": "Can gust (inspect) one person during the day. Can flood (kill) one person during the day (user is not revealed). Can't be poisoned. Vote of 500. Sided with Nature.",
			"actions": {
				"standby": {
					"gust": {
						"command": "expose",
						"target": "AnyButTeam",
						"msg": "Use /gust [name] to find out someone's role! This will be revealed only to you.",
						"exposedtargetmsg": "Your wind was strong, but ~Target~ was able to withstand it, proving them to be quite a strong ~Role~!",
						"exposemsg": "Whoosh! A fierce wind blew past, almost knocking down a ~Role~!"
					},
					"flood": {
						"command": "kill",
						"target": "AnyButTeam",
						"msg": "You can also kill someone using /flood [name]! This won't reveal you either!",
						"killmsg": "The hurricane is fierce, and fast. Suddenly, the cries of ~Target~ are heard, and everyone turns to see ~Target~ washed away in the raging waters of the storm, never to be seen again."
					}
				},
				"vote": 500,
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true
			},
			"winIfDeadRoles": [
				"alien",
				"aliencured",
				"alienp",
				"alienm",
				"alienmcured",
				"alienmp",
				"ufo",
				"alcohol",
				"alcoholcured",
				"alcoholp",
				"heroin",
				"heroincured",
				"heroinp",
				"meth",
				"methcured",
				"methp",
				"chief",
				"chiefcured",
				"chiefp",
				"indian",
				"indiancured",
				"indianp",
				"infector",
				"mafia2",
				"mafia2cured",
				"mafia2p",
				"savage",
				"savagecured",
				"savagep",
				"vigilante",
				"vigilantecured",
				"vigilantep",
				"samurai",
				"samuraicured",
				"samuraip",
				"joat",
				"joatcured",
				"joatp"
			]
		},
		{
            "role": "raincured",
            "translation": "Rain",
            "side": "nature",
			"hide": true,
            "help": "You have been cured and live to see another day! Drip  drip drop. You are the symbol of nature's tears. You have the ability  to /safeguard one person during the night. During the day, you can  /expose someone to rain down on them and determine their role (their  role will be revealed only to you). Since you are the medium for Thunder  and Lightning, if you die, they will die with you. You are the sacred weapon to your team, so you have a 1.1 vote.",
            "info": "Can safeguard one person during the night. Can expose (inspect) one person during the standby. Sided with Nature.",
            "actions": {
                "standby": {
                    "expose": {
                        "target": "AnyButTeam",
                        "msg": "You can type /expose [name] to find out someone's role! This will only be revealed to you.",
                        "exposedtargetmsg": "You landed on ~Target~ and they shook you off, so you found out they were a ~Role~.",
                        "exposemsg": "The rain started to fall harder and everyone felt a chill go down their spines."
                    }
                },
                "night": {
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 1
                    }
                },
                "vote": 1.1,
                "onDeath": {
                    "killRoles": [
                        "light",
                        "thunder",
                        "lightp",
                        "thunderp"
                    ]
                }
            }
        },
        {
            "role": "rainp",
            "translation": "Rain",
            "side": "nature",
			"hide": true,
            "help": "You  have been infected with the virus, and unless you're cured, you will  die the next night! However, you yourself may spread the virus in hopes  of infecting those not on your team using /infect, but you can only do  this once! Drip drip drop. You are the symbol of nature's tears. You  have the ability to /safeguard one person during the night. During the  day, you can /expose someone to rain down on them and determine their  role (their role will be revealed only to you). Since you are the medium  for Thunder and Lightning, if you die, they will die with you.You are the sacred weapon to your team, so you have a 1.1 vote ",
            "info": "Can safeguard one person during the night. Can expose (inspect) one person during the standby. Sided with Nature.",
            "actions": {
                "standby": {
                    "expose": {
                        "target": "AnyButTeam",
                        "msg": "You can type /expose [name] to find out someone's role! This will only be revealed to you.",
                        "exposedtargetmsg": "You landed on ~Target~ and they shook you off, so you found out they were a ~Role~.",
                        "exposemsg": "The rain started to fall harder and everyone felt a chill go down their spines."
                    }
                },
                "night": {
                    "safeguard": {
                        "target": "AnyButSelf",
                        "common": "Self",
                        "priority": 1
                    },
                    "infect": {
                        "command": [
                            "convert",
                            "poison"
                        ],
                        "target": "AnyButTeam",
                        "common": "Self",
                        "priority": 7,
                        "broadcast": "team",
                        "newRole": {
                            "villagerp": [
                                "villager",
                                "villagercured"
                            ],
                            "detoxerp": [
                                "detoxer",
                                "detoxercured"
                            ],
                            "rainp": [
                                "rain",
                                "raincured"
                            ],
                            "stalkerp": [
                                "stalker",
                                "stalkercured"
                            ],
                            "inspectorp": [
                                "inspector",
                                "inspectorcured"
                            ],
                            "inspector2p": [
                                "inspector2",
                                "inspector2cured"
                            ],
                            "bodyguardp": [
                                "bodyguard",
                                "bodyguardcured"
                            ],
                            "bodyguard2p": [
                                "bodyguard2",
                                "bodyguard2cured"
                            ],
                            "spyp": [
                                "spy",
                                "spycured"
                            ],
                            "mayorp": [
                                "mayor",
                                "mayorcured"
                            ],
                            "exposerp": [
                                "exposer",
                                "exposercured"
                            ],
                            "neighborp": [
                                "neighbor",
                                "neighborcured"
                            ],
                            "samuraip": [
                                "samurai",
                                "samuraicured"
                            ],
                            "vigilantep": [
                                "vigilante",
                                "vigilantecured"
                            ],
                            "hookerp": [
                                "hooker",
                                "hookercured"
                            ],
                            "joatp": [
                                "joat",
                                "joatcured"
                            ],
                            "millerp": [
                                "miller",
                                "millercured"
                            ],
                            "mafia2p": [
                                "mafia2",
                                "mafia2cured"
                            ],
                            "infectorp": [
                                "infector",
                                "infectorcured"
                            ],
                            "savagep": [
                                "savage",
                                "savagecured"
                            ],
                            "methp": [
                                "meth",
                                "methcured"
                            ],
                            "alcoholp": [
                                "alcohol",
                                "alcoholcured"
                            ],
                            "heroinp": [
                                "heroin",
                                "heroincured"
                            ],
                            "alienp": [
                                "alien",
                                "aliencured"
                            ],
                            "ufop": [
                                "ufo",
                                "ufocured"
                            ],
                            "alienmp": [
                                "alienm",
                                "alienmcured"
                            ],
                            "indianp": [
                                "indian",
                                "indiancured"
                            ],
                            "chiefp": [
                                "chief",
                                "chiefcured"
                            ],
                            "headp": [
                                "head",
                                "headcured"
                            ],
                            "lightp": [
                                "light",
                                "lightcured"
                            ],
                            "thunderp": [
                                "thunder",
                                "thundercured"
                            ],
                            "light2p": [
                                "light2",
                                "light2cured"
                            ],
                            "thunder2p": [
                                "thunder2",
                                "thunder2cured"
                            ],
							"bombnightp": [
								"bombnight",
								"bombnightcured"
							],
							"bombdayp": [
								"bombday",
								"bombdaycured"
							],
							"bombvotep": [
								"bombvote",
								"bombvotecured"
							],
							"chiefstrongp": [
								"chiefstrong",
								"chiefstrongcured"
							],
							"villager3p": [
                                "villager3",
                                "villager3cured"
                            ]
                        },
                        "silent": true,
						
                        "pierce": true,
						"hide": true,
                        "charges": 1,
						"usermsg": "You have infected ~Target~!",
                        "poisonDeadMessage": "You have been another victim of the virus! The dreaded outbreak continues..."
                    }
                },
                "vote": 1.1,
                "onDeath": {
                    "killRoles": [
                        "light",
                        "thunder",
                        "lightp",
                        "thunderp"
                    ]
                }
            }
        },
		{
			"role": "infectedrole",
			"translation": "Any Infected Role",
			"side": "mafia",
			"help": "Placeholder role for /priority formatting",
			"hide": true,
			"actions": {
				"night": {
					"infect": {
						"command": "kill",
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 7,
						"broadcast": "team"
					}
				}
			}
		}
    ],
	"roles1": [
		"bombday",
		"samurai",
		"ufo"
	],
	"roles2": [
		"bombnight",
		"vigilante",
		"bodyguard",
		"savage"
	],
	"roles3": [
        "samurai",
        "bombnight",
        "ufo",
        "infectorsmall",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "bodyguard"
	],
    "roles4": [
        "samurai",
        "bombnight",
        "ufostrong",
        "infector",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "bodyguard",
        "meth",
        "alcohol",
        {
			"villager": 0.75,
			"villager3": 0.25
		}
    ],
    "roles5": [
        {
			"inspector": 0.5,
			"inspector2": 0.5
		},
        "bodyguard2",
        "hooker",
        "alcohol",
        "meth",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "alien",
        "alienm",
        "infector",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "heroin",
		{
			"stalker": 0.4,
			"exposer": 0.3,
			"samurai": 0.3
		},
        "spy",
        "ufo",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "savage",
        "joat",
        "mayor",
        "chiefstrong"
    ],
    "roles6": [
        {
			"inspector": 0.5,
			"inspector2": 0.5
		},
        "bodyguard2",
        "hooker",
        "mayor",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "heroin",
        "alcohol",
        "meth",
        "alienm",
        "ufo",
        "alien",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "chief",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "neighbor",
        "spy",
        "joat",
        {
			"stalker": 0.4,
			"exposer": 0.3,
			"samurai": 0.3
		},
        "savage",
        "head",
        "infector",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "mafia2",
        "detoxer",
        "vigilante",
        "indian",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
		"miller"
    ],
    "roles7": [
        {
			"inspector": 0.5,
			"inspector2": 0.5
		},
        "bodyguard2",
        "hooker",
        "mayor",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "heroin",
        "alcohol",
        "meth",
        "alienm",
        "ufo",
        "alien",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "chief",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "neighbor",
        "spy",
        "joat",
        "detoxer",
        "savage",
        "head",
        "infector",
        "rain",
        "mafia2",
        {
			"stalker": 0.4,
			"exposer": 0.3,
			"samurai": 0.3
		},
        "vigilante",
        "indian",
        "light",
        "thunder",
        {
			"villager": 0.75,
			"villager3": 0.25
		}
    ],
	"roles8": [
        {
			"inspector": 0.5,
			"inspector2": 0.5
		},
        "bodyguard2",
        "hooker",
        "mayor",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "heroin",
        "alcohol",
        "meth",
        "alienm",
        "ufo",
        "alien",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "chief",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "neighbor",
        "spy",
        "joat",
        "detoxer",
        "savage",
        "head",
        "infector",
        "rain",
        "mafia2",
        {
			"stalker": 0.7,
			"samurai": 0.3
		},
        "vigilante",
        "indian",
        "light",
        "thunder",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "exposer",
		"miller",
		"alcohol"
    ],
	"roles9": [
        {
			"inspector": 0.5,
			"inspector2": 0.5
		},
        "bodyguard2",
        "hooker",
        "mayor",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "heroin",
        "alcohol",
        "meth",
        "alienm",
        "ufo",
        "alien",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "chief",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "neighbor",
        "spy",
        "joat",
        "detoxer",
        "savage",
        "head",
        "infector",
        "rain",
        "mafia2",
        "stalker",
        "vigilante",
        "indian",
        "light",
        "thunder",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "exposer",
        "miller",
        "alcohol",
        "samurai",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "indian",
        "bombnight",
        {
			"villager": 0.75,
			"villager3": 0.25
		},
        "alien",
		"miller",
		"vigilante",
		"infector",
		"thunder",
		{
			"villager": 0.75,
			"villager3": 0.25
		},
		"ufo",
		"samurai"
    ],
    "villageCantLoseRoles": [
        "mayor",
        "mayorp",
        "mayorcured",
        "vigilante",
        "vigilantep",
        "vigilantecured",
        "samurai",
        "samuraip",
        "samuraicured",
        "joat",
        "joatp",
        "joatcured"
    ],
    "changelog": [
        "4/3/14: Theme created.",
        "5/17/14: Fixed the Infector and made it able to infect people. Changed Agent side to Drug Dealers. Made the Indians side rely less on chance. Renamed village roles. Created Medic.",
        "5/22/14: Fixed the errors in messages and the Mafia side.",
		"6/21/14: Edited spawn to have Infector spawn earlier with Salesman spawning later. Medic added to spawn.",
		"6/22/14: Fixed the /infect command. Cleaned up the priority list. Renamed the Mafia side (now called the Outbreak).",
		"6/25/14: Created and added Chemist. Removed Meth Dealer's 10% fail chance for /meth (distract). Removed President's hax (protect). Gave President and First Lady startup reveal and /tt between themselves. Swapped Heroin Addict for Alcoholic in 10 player game spawn. Reduced Lightning's kills per night from 3 to 2. Removed Savage's 20% chance to evade nightkills. Removed Head Shrinker's kill and gave it a -2 voteshield. If lynched, Heroin Addict can now kill one person before dying, outspeeding bodyguards and distractors. Mafia role renamed to Outbreak Mastermind.",
		"6/25/14: Changed some of the roles that Heroin Addict can fake expose people as.",
		"6/28/14: Changed small game spawn to include an Infector that can only infect. Regular Alien now gets hax on protect. Alien Mesmerizer can now inspect (reveals side). Infector now has a 50% chance to evade nightkills in games of 13 and more.",
		"7/1/14: Minor grammatical changes in role infos. Infector, Rain, Thunder, and Lightning can no longer be poisoned. The Heroin Addict ignores detox after being lynched.",
		"7/4/14: 'MURICA DAY! Tips added. Meth Dealer's /meth (distract) is now broadcasted to its teammates. Alien Mesmerizer's /distract is now broadcasted to its teammates. That's it.",
		"7/4/14: Small game spawn (games of 10 or less) completely revamped to avoid dull and slow games. UFO, Soldier, and Chemist now appear in small games. In games of 8 through 10, the UFO now evades one nightkill.",
		"7/4/14: Tweaked spawn just a bit to include the Infector in all games, regardless of player count. Regular Alien now gets hax on distract.",
		"7/4/14: Game expanded to include 3 or 4 players.",
		"7/5/14: Huge changes to spawn list, allowing the Indian side and Nature side to come in sooner. Hoodlum now reveals as any mafia role when inspected. Created a stronger version of Chieftain in games of 20 when it is alone; it can /ambush (kill that bypasses protect) once a game, can't be distracted, and evades one nightkill.",
		"7/5/14: Rain converts into Hurricane (kuja with a daytime inspect and a daykill) if both Lightning and Thunder are dead.",
		"7/13/14: Alien Mesmerizer's inspect reveals the target's role instead of just their side. Soldier's number of revealing daykills per game increased from 2 to 3.",
		"7/19/14: In games of 13 through 29, Detective only has a 40% chance of spawning, while Firefighter and Soldier each have a 30% chance of spawning. In games of 30 through 32, Detective only has a 70% chance of spawning, while Soldier has a 30% chance of spawning.",
		"7/23/14: Swapped a few priorities because the convert from /infect was messing up roles. Prevent Teamvote added.",
		"7/26/14: Every Civilian that spawns now has a 25% chance to gain the ability to kill instead of expose if they are lynched (everyone is told they can expose when lynched though). Lightning's kills can no longer be haxed."
    ]
}
